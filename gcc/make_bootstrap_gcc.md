

--without-headers: 交叉编译器还不需要目标板头文件，否则会有很多*.h的头文件找不到。  

--disable-shared: 既然是第一次安装ARM交叉编译工具，那么本机的glibc支持的应该是本机的编译工具库，而不是ARM交叉编译工具库。force GCC to link its internal libraries statically, 没有这个选项，会有crti.o: No such file: No such file or directory collect2: ld returned 1 exit status

一下选项都需要libc支持：
* --disable-multilib
* --disable-threads 
* --disable-decimal-float 
* --disable-libmudflap   边界检查使用的库
* --disable-libssp       边界检查使用的库

```shell
. ~/xtools/scropt/buildrc

ln -s $GMP_SRC $GCC_SRC/gmp
ln -s $MPC_SRC $GCC_SRC/mpc
ln -s $MPFR_SRC $GCC_SRC/mpfr
ln -s $M4_SRC $GCC_SRC/m4

cd $GCC_BLD_PATH

$GCC_SRC/configure \
--build=$HOST \
--host=$HOST \
--target=$TARGET \
--prefix=$PREFIX \
--enable-languages=c,c++ \
--disable-multilib \
--disable-threads \
--disable-shared \
--disable-decimal-float \
--disable-libmudflap \
--disable-libssp \
--without-headers


make -j2 all-gcc

make install-gcc

```