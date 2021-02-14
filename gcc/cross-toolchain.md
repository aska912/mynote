# 编译 gcc工具链命令 for arm

```shell
 # ./../configure -v \
--build=x86_64-build_pc-linux-gnu \
--host=x86_64-build_pc-linux-gnu \
--target=arm-linux-gnueabihf \
--prefix=/opt/gcc/8.3.0 \
--enable-languages=c,c++ \
--enable-checking=release \
--disable-multilib \
--enable-shared \
--enable-long-long s \
--enable-threads=posix \
--with-host-libstdcxx='-static-libgcc -Wl,-Bstatic,-lstdc++,-Bdynamic -lm' \
--program-suffix=-8.3 

# make -j4
# sudo make install
```

```shell
./../configure -v \
--build=x86_64-linux-gnu \
--host=x86_64-linux-gnu \
--target=aarch64-linux-gnueabihf \
--prefix=/opt/gcc/8.3.0 \
--enable-languages=c,c++ \
--enable-checking=release \
--disable-multilib \
--enable-shared \
--enable-long-long s \
--enable-threads=posix \
--with-arch=armv8 \
--with-float=hard \
--with-fpu=vfp \
--program-suffix=-8.3 
```