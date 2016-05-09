#Five Special Secrets of Linking with Libraries

### 1. Dynamic libraries are called lib something .so , and static libraries are
called lib something .a

By convention, all dynamic libraries have a filename of the form libname .so
(version numbers may be appended to the name). Thus, the library of thread routines
is called libthread .so . A static archive has a filename of the form libname.a.
Shared archives, with names of the form libname .sa , were a transient
phenomenon, helping in the transition from static to dynamic libraries. Shared
archives are also obsolete now.

### 2. You tell the compiler to link with, for example, libthread.so by giving the
option -lthread

The command line argument to the C compiler doesn't mention the entire pathname to
the library file. It doesn't even mention the full name of the file in the library
directory! Instead, the compiler is told to link against a library with the command line
option -lname where the library is called libname .so —in other words, the
" lib " part and the file extension are dropped, and -l is jammed on the beginning
instead.

### 3. The compiler expects to find the libraries in certain directories

At this point, you may be wondering how the compiler knows in which directory to
look for the libraries. Just as there are special rules for where to find header files, so
the compiler looks in a few special places such as /usr/lib/ for libraries. For
instance, the threads library is in /usr/lib/libthread.so .
The compiler option -Lpathname is used to tell the linker a list of other directories
in which to search for libraries that have been specified with the -l option. There are
a couple of environment variables, LD_LIBRARY_PATH and LD_RUN_PATH,
that can also be used to provide this information. Using these environment variables is
now officially frowned on, for reasons of security, performance, and build/execute
independence. Use the -Lpathname -Rpathname options at linktime instead.

### 4. Identify your libraries by looking at the header files you have used

Another key question that may have occurred to you is, "How do I know which
libraries I have to link with?" The answer, as (roughly speaking) enunciated by Obi-
Wan Kenobi in Star Wars, is, "Use the source, Luke!" If you look at the source of
your program, you'll notice routines that you call, but which you didn't implement. For
example, if your program does trigonometry, you've probably called routines with
names like sin() or cos() , and these are found in the math library. The manpages
show the exact argument types each routine expects, and should mention the library
it's in.
A good hint is to study the #include s that your program uses. Each header file that
you include potentially represents a library against which you must link. This tip
carries over into C++, too. A big problem of name inconsistency shows up here.
Header files usually do not have a name that looks anything like the name of the
corresponding library. Sorry! This is one of the things you "just have to know" to be a
C wizard. Table 5-1 shows examples of some common ones.

Table 5-1. Library Conventions Under Solaris 2.x

| #include Filename              | Library Pathname            | Compiler Option to Use |
|:-------------------------------|:----------------------------|:-----------------------|
| \<math.h\>                     |  /usr/lib/libm.so           | -lm
| \<math.h\>                     |  /usr/lib/libm.a            | -dn -lm
| \<stdio.h\>                    |  /usr/lib/libc.so           | linked in automatically
| "/usr/openwin/include/X11.h"   |  /usr/openwin/lib/libX11.so | -L/usr/openwin/lib<br>-lX11
| \<thread.h\>                   |  /usr/lib/libthread.so      | -lthread
| \<curses.h\>                   |  /usr/ccs/lib/libcurses.a   | -lcurses
| \<sys/socket.h\>               |  /usr/lib/libsocket.so      | -lsocket


Another inconsistency is that a single library may contain routines that satisfy the
prototypes declared in multiple header files. For example, the functions declared in the
header files <string.h> , <stdio.h> , and <time.h> are all usually
supplied in the single library libc.so . If you're in doubt, use the nm utility to listthe routines that a library contains.
