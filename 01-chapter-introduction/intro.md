# 简介
> Julia 对我来说不仅仅是一个像 Python 一样可以快速刷代码，运行速度目前可以达到 C 的2~3倍，还可以像 R，Matlab，Fortran 一样用户友好，特别为科学计算优化的编程语言。Julia由于代码易读，Julia base 基本上都是由Julia本身实现的，计算机菜鸟们可以通过阅读优质Julia代码，快速提升自己。
> ————郭兰亭，海普洛斯，生物信息工程师，机器学习与深度学习组负责人

## 介绍
Julia 是一款为科学计算（technical computing）而设计的编程语言。它的语法和其它科学计算语言的语法也有很多相似之处，简单易学。Julia提供了一个复杂精巧的编译器，分布式的并行计算环境，精确的数值计算，以及一个可扩展的数学函数库。Julia的基本库在线性代数，随机数产生器，信号处理和字符串处理方面引入了很多在单项表现极佳，成熟的开源 C/Fortran 库之外，大部分是使用 Julia 语言本身完成的。特别地，Julia 的开发者社区正在快速地通过 Julia 内建的包管理器添加着各种外部扩展包。

## 特点
- 多重派发：提供为多种类型定义函数的能力
- 动态的类型系统：方便程序文档化，优化和分派
- 高性能，接近静态编译语言，如 C 语言
- 内置的包管理器
- 像 Lisp 一样真正的宏以及其它元编程特性
- 可以自由地通过 PyCall 调用 Python 程序
- 直接掉用 C 语言：不需要封装或者特别的 API
- Shell 一样强大的管理其他进程的能力
- 为分布式和并行计算所设计
- 轻量级“绿色”线程（协程）
- 用户定义的类型和内建类型一样快
- Automatic generation of efficient, specialized code for different argument types
- 美观可扩展的类型转换与提升
- 高效支持 Unicode, 包括且不只 UTF-8
- 免费开源（MIT 协议）

## 高性能JIT编译器
以下是 Julia 官网做的性能测试。
性能测试是相对于 C 语言的，数值越小越好，C 的性能为1。

|   |Fortran|Julia|Python|R|Matlab|Octave|Mathe-matica|JavaScript|Go|LuaJIT|Java|
|---|-------|---|---|---|---|---|---|---|---|---|---|
|   |gcc 5.1.1 |  0.4.0 |  3.4.3 | 3.2.2 | R2015b | 4.0.0 | 10.2.0 | V8 3.28.71.19  | go1.5  | gsl-shell 2.3.1 | 1.8.0_45|
|fib|0.70|2.11|77.76|533.52|26.89|9324.35|118.53|3.36|1.86|1.71|1.21|
|parse_int|5.05|1.45|17.02|45.73|802.52|9581.44|15.02|6.06|1.20|5.77|3.3|
|quicksort|1.31|1.15|32.89|264.54|4.92|1866.01|43.23|2.70|1.29|2.03|2.60|
|mandel|0.81|0.79|15.32|53.16|7.58|451.81|5.13|0.66|1.11|0.67|1.35|
|pi_sum|1.00|1.00|21.99|9.56|1.00|299.31|1.69|1.01|1.00|1.00|1.00|
|rand_mat_stat|1.45|1.66|17.93|14.56|14.52|30.93|5.95|2.30|2.96|3.27|3.92|
|rand_mat_mul|3.48|1.02|1.14|1.57|1.12|1.12|1.30|15.07|1.42|1.16|2.36|
