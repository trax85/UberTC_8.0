**README**

Repository link : https://bitbucket.org/matthewdalex/aarch64-linux-android-8.x/src/master/                                             
Type in terminal : ``` git clone https://bitbucket.org/matthewdalex/aarch64-linux-android-8.x.git ```

To compile Kernel using this toolchain :
``` 
export ARCH=arm64 
export CROSS_COMPILE="/home/User/aarch64-linux-android-8.x/bin/aarch64-linux-android- 
```

This Toolchain is isl enabled so supports graphite optimizations, these optimizations can be used in your makefile 
```-fgraphite, -fgraphite-identity, -floop-nest-optimize, -floop-parallelize-all ```
Using the above optimizations requires you to have stack protector as strong, Make these changes in the defconfig of your device
```
# CONFIG_CC_STACKPROTECTOR_REGULAR is not set
CONFIG_CC_STACKPROTECTOR_STRONG=y
```
Make sure to check out https://gcc.gnu.org/onlinedocs/gcc/Optimize-Options.html for all the options available with GCC. And remember to fix all issues and warnings the compiler throws at you.
