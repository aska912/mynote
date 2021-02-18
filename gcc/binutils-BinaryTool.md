Binutils工具安装依赖于Bash、Coreutils、Diffutils、GCC、Gettext、Glibc、Grep、Make、Perl、Sed、Texinfo等工具。
 
Binutils是GNU工具之一，它包括连接器、汇编器和其他用于目标文件和档案的工具，它是二进制代码的处理维护工具。安装Binutils工具包含的程序有addr2line、ar、as、c++filt、gprof、ld、nm、objcopy、objdump、ranlib、readelf、size、strings、strip、libiberty、libbfd和libopcodes。对这些程序的简单解释如下。

* ar  建立、修改、提取归档文件。归档文件是包含多个文件内容的一个大文件，其结构保证了可以恢复原始文件内容。
* as  主要用来编译GNU C编译器gcc输出的汇编文件，产生的目标文件由连接器ld连接。
* c++filt  连接器使用它来过滤 C++ 和 Java 符号，防止重载函数冲突。
* gprof  显示程序调用段的各种数据。
* ld  是连接器，它把一些目标和归档文件结合在一起，重定位数据，并连接符号引用。通常，建立一个新编译程序的最后一步就是调用ld。
* nm  列出目标文件中的符号。
* objcopy  把一种目标文件中的内容复制到另一种类型的目标文件中。
* objdump  显示一个或者更多目标文件的信息。使用选项来控制其显示的信息。
* ranlib  产生归档文件索引，并将其保存到这个归档文件中。在索引中列出了归档文件各成员所定义的可重分配目标文件。
* readelf  显示elf格式可执行文件的信息。
* size  列出目标文件每一段的大小以及总体的大小。默认情况下，对于每个目标文件或者一个归档文件中的每个模块只产生一行输出。
* strings  打印某个文件的可打印字符串，这些字符串最少4个字符长，也可以使用选项-n设置字符串的最小长度。默认情况下，它只打印目标文件初始化和可加载段中的可打印字符；对于其它类型的文件它打印整个文件的可打印字符。这个程序对于了解非文本文件的内容很有帮助。
* strip  丢弃目标文件中的全部或者特定符号。
* libiberty  包含许多GNU程序都会用到的函数，这些程序有getopt、obstack、strerror、strtol和strtoul。
* libbfd  二进制文件描述库。
* libopcode  用来处理opcodes的库，在生成一些应用程序的时候也会用到它。
  
  
```shell
$BINUTILS_SRC/configure --target=$TARGET --prefix=$TARGET_PREFIX
make
make install
```