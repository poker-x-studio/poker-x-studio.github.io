---
title: "Go项目,传递bool类型的命令行参数(flag)时需要留意的"
date: 2023-08-26
categories: 
  - "go"
  - "linux"
---

### 一 这里命令行参数解析使用的是第三方包 go-flags

#### github地址 [https://github.com/jessevdk/go-flags](https://github.com/jessevdk/go-flags)

在README.md文件中，有部分关于bool类型的说明

```
var opts struct {
    // Slice of bool will append 'true' each time the option
    // is encountered (can be set multiple times, like -vvv)
    Verbose []bool `short:"v" long:"verbose" description:"Show verbose debug information"`
}
```

This specifies one option with a short name -v and a long name --verbose. When either -v or --verbose is found on the command line, a 'true' value will be appended to the Verbose field. e.g. when specifying -vvv, the resulting value of Verbose will be {[true, true, true]}.

#### 【只要在命令行中找到 -v 或--verbose，那么，参数对应的值就是 true】

#### 【如果需要设置false，则 去掉 -v 或--verbose 就好】

```
// Make some fake arguments to parse.
args := []string{
    "-vv",
}

fmt.Printf("Verbosity: %v\n", opts.Verbose)

// Output: Verbosity: [true true]
```

### 二 在 vscode中的具体使用

- launch.json 中设置
    
    ```
    "configurations": [
        {
            "name": "lobby_server",
            "type": "go",
            "request": "launch",
            "mode": "auto",
            "program": "${workspaceFolder}/cmd/lobby_server",
            "args": [
                "--debug",//bool flag只要设置 short或long,值就是true
                "--lobby_config_file","lobby_8101.toml",
            ]
        },
    ```
    

main.go 文件

```
import(
"github.com/jessevdk/go-flags"
)

// 命令行参数
type CmdParams struct {
    Debug             bool   `short:"d" long:"debug" description:"是否debug"`
    Lobby_config_file string `short:"l" long:"lobby_config_file" description:"大厅配置文件"`
}

func main() {
    defer func() {
        if err := recover(); err != nil {
            fmt.Println(err)
        }
    }()

    //解析参数
    var cmd_params CmdParams
    if _, err := flags.Parse(&cmd_params); err != nil {
        panic("Parse err:" + err.Error())
    }

    if !cmd_params.Debug {
        xdebug.Set_release()
    }

    //...
}
```

### 三 调试跟踪代码

具体可详细查看 函数 parseOption

```
func (p *Parser) parseOption(s *parseState, name string, option *Option, canarg bool, argument *string) (err error) {
    if !option.canArgument() {//bool类型 不能带参数
        if argument != nil {
            return newErrorf(ErrNoArgumentForBool, "bool flag `%s' cannot have an argument", option)
        }

        err = option.set(nil)
    } else if argument != nil || (canarg && !s.eof()) {
    //...
    }
    //....
}   

func (option *Option) canArgument() bool {
    if u := option.isUnmarshaler(); u != nil {
        return true
    }

    return !option.isBool()
}

//运行参数是否是bool类型
func (option *Option) isBool() bool {
    tp := option.value.Type()

    for {
        switch tp.Kind() {
        case reflect.Slice, reflect.Ptr:
            tp = tp.Elem()
        case reflect.Bool:
            return true
        case reflect.Func:
            return tp.NumIn() == 0
        default:
            return false
        }
    }
}
```

--the end
