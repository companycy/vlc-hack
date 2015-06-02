
<!-- refer to official guide -->
<!-- vlc 2.1.5 -->
<!-- build for win32 -->
<!-- pass on centos6.4 -->

https://wiki.videolan.org/Win32Compile/

<!-- remove below config in configure.ac -->
configure.ac: error-implicit-function-declaration

<!-- patch for 2.1.5, refer to mod.patch -->
https://mailman.videolan.org/pipermail/vlc-devel/2014-June/098371.html

<!-- /bin/sh: 1: i686-w64-mingw32-gcc: not found -->
sudo apt-get install -y gcc-mingw-w64-i686 g++-mingw-w64-i686 mingw-w64-tools
<!-- also, need 3.0 or later mingw-w64, refer to deb under player dir -->

sudo apt-get install -y ua5.1 libtool automake autoconf autopoint make gettext pkg-config qt4-dev-tools qt git subversion cmake cvs zip p7zip-full nsis bzip2


<!-- for ubuntu 12.04, require luac 32-bit -->
cp /usr/bin/luac /home/bjcheny/vlc/contrib/i686-w64-mingw32/bin/luac


<!-- for latest vlc, it's required -->
sudo apt-get install -y protobuf-compiler


<!-- for time stamp issue -->
sudo apt-get install ntpdate
ntpdate cn.pool.ntp.org




--enable-debug --disable-optimizations
bjcheny@bjcheny-win7-1 ~/vlc-2.1.5/win32
$ vi Makefile


https://mailman.videolan.org/pipermail/vlc-devel/2011-April/079084.html
http://comments.gmane.org/gmane.comp.video.videolan.vlc.devel/89286


https://forum.videolan.org/viewtopic.php?f=14&t=76036
Openssl
./Configure --cross-compile-prefix=/usr/bin/i586-mingw32msvc- mingw shared
make
cp *.a /usr/i586-mingw32msvc/lib/
cp *.dll /usr/i586-mingw32msvc/bin/
cp include/openssl /usr/i586-mingw32msvc/include/


CFLAGS = -g -O2 -I/home/bjcheny/vlc-2.1.5/contrib/i686-w64-mingw32/include -mms-bitfields -Wall -Wextra -Wsign-compare -Wundef -Wpointer-arith -Wbad-function-cast -Wwrite-strings -Wmissing-prototypes -Wvolatile-register-var -pipe -ffast-math -funroll-loops -fomit-frame-pointer
CXXFLAGS = -g -O2 -I/home/bjcheny/vlc-2.1.5/contrib/i686-w64-mingw32/include -mms-bitfields -Wall -Wextra -Wsign-compare -Wundef -Wpointer-arith -Wvolatile-register-var -ffast-math -funroll-loops -fomit-frame-pointer


CFLAGS="-static-libgcc -static-libstdc++" ../extras/package/win32/configure.sh --host=i686-w64-mingw32


export LUA=/usr/bin/lua32
export LUAC=/usr/bin/luac32

if_nametoindex to atoi



1. static link failed, package libgcc_s_sjlj-1.dll and libstdc++-6.dll
2. qt failed

cp -r /home/bjcheny/vlc-2.1.5/win32/_win32/lib/vlc/plugins /home/bjcheny/vlc-2.1.5/win32/vlc-2.1.5
