# Julia 旅程
在前面的章节中，我们配置的了 Julia 环境，因为 Julia 允许交互式编程，所以本章节大部分情况下是在交互式界面编写程序，如果需要编写 Julia 脚本，请选择一个适合你的编辑器编写 Julia 代码（笔者使用 sublime 编辑器）。

## HelloJulia

在配置好 Julia 环境之后，在命令输入 julia 命令会进入 Julia 的交互环境。
笔者使用的系统是 win10。所以以后所有命令行命令都是在 powershell 的 `PS:` 标识后运行。
> PS: julia  

```               _
   _       _ _(_)_     |  A fresh approach to technical computing
  (_)     | (_) (_)    |  Documentation: http://docs.julialang.org
   _ _   _| |_  __ _   |  Type "?help" for help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 0.5.0-dev+4046 (2016-05-12 05:13 UTC)
 _/ |\__'_|_|_|\__'_|  |  Commit 38bdc6e (0 days old master)
|__/                   |  x86_64-w64-mingw32

julia>
```
如果你使用是的 linux 系统，会显示如下，这是我司服务器上运行的 Julia。
> ~$ julia

```
               _
   _       _ _(_)_     |  A fresh approach to technical computing
  (_)     | (_) (_)    |  Documentation: http://docs.julialang.org
   _ _   _| |_  __ _   |  Type "?help" for help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 0.5.0-dev+4009 (2016-05-10 01:30 UTC)
 _/ |\__'_|_|_|\__'_|  |  Commit b39a550* (2 days old master)
|__/                   |  x86_64-linux-gnu

julia> 
```
我们在 powershell 运行一下下面这条命令
> PS: julia -e 'println("Hello Julia")'  

这时候出现了错误：
```
ERROR: syntax: missing comma or ) in argument list
 in eval(::Module, ::Any) at .\boot.jl:230
 [inlined code] from .\sysimg.jl:11
 in process_options(::Base.JLOptions) at .\client.jl:240
 in _start() at .\client.jl:319
```
那我们在服务器上的 linux 系统运行同样的命令。
> ~$ julia -e 'println("Hello Julia")'

这时候输出了 `Hello Julia`

>所以在 win10 的稳定的 bash 版出来之前，还是默默的时候用 mac 或者 linux 作为开发环境吧。当然如果你不需要本地测试，现在的 windows 系统还是不错的开发环境。笔者喜欢 win10 下写完代码传到服务器上测试。  

我们还是尽量不要使用上面的方法来实验代码，潜在的问题有很多，如果只是需要简单的测试实验，julia 的交互式操作是不错的。
本章以后所有的 julia 交互代码，都运行在 `julia>` 标识之后。

> julia> print("hello julia")  
> hello julia  
> julia> println("hello julia")  
> hello julia  
>  
> julia> "hello julia"  
> "hello julia"  

从上面的代码可以看出，在 julia 交互模式下，几种输出 `hello julia` 的区别。

接下来，我看看运行编写 julia 脚本的情况。
先创建 doing 目录，在目录下创建 hellojulia.jl 脚本 
> PS: mkdir doing  
> PS: cd doing  
> PS: notepad hellojulia.jl # subl hellojulia.jl  

在 hellojulia.jl 脚本中编写代码
```julia
print("hello julia")
println("hello julia")
"hello julia"
```
运行脚本
> PS: julia hellojulia.jl  
> hello juliahello julia  

我们可以看到相同的代码，在脚本中运行和在交互式中运行是有差别的。