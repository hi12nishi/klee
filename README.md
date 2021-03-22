KLEE Symbolic Virtual Machine
=============================

[![Build Status](https://travis-ci.com/klee/klee.svg?branch=master)](https://travis-ci.com/klee/klee)
[![Build Status](https://api.cirrus-ci.com/github/klee/klee.svg)](https://cirrus-ci.com/github/klee/klee)
[![Coverage](https://codecov.io/gh/klee/klee/branch/master/graph/badge.svg)](https://codecov.io/gh/klee/klee)

`KLEE` is a symbolic virtual machine built on top of the LLVM compiler
infrastructure. Currently, there are two primary components:

  1. The core symbolic virtual machine engine; this is responsible for
     executing LLVM bitcode modules with support for symbolic
     values. This is comprised of the code in lib/.

  2. A POSIX/Linux emulation layer oriented towards supporting uClibc,
     with additional support for making parts of the operating system
     environment symbolic.

Additionally, there is a simple library for replaying computed inputs
on native code (for closed programs). There is also a more complicated
infrastructure for replaying the inputs generated for the POSIX/Linux
emulation layer, which handles running native programs in an
environment that matches a computed test input, including setting up
files, pipes, environment variables, and passing command line
arguments.

For further information, see the [webpage](http://klee.github.io/).

## Added option (by hi12nishi)
* -write-print-expr
  - klee_print_expr関数で出力される計算式を実行パスごとに出力する(出力ファイル: test00000N.expr)
* -output-exec-tree
  - Kleeのprocess treeをダンプする
  - KennyMacheka によるKleeのfork(print-csv-treeブランチ)の実装を元に作成 (https://github.com/KennyMacheka/klee/tree/print-csv-tree)
