# goDLL
Project to show people how to create MS Windows golang DLL, then load it into lazarus program, or a plain fpc command line program or another golang exe

Current way of making a DLL:
* compile go code with regular go compiler and put that code into .a and .h files. These are just like C code that GCC can use, but stored in compiled .a and .h files
* then build a dll based on the dummy .c file that just links the .a and .h files (go code) into a dll, using GCC to build the dll

Well known issues with Go DLL's:

* AFAIK you can only add one go dll to a program, and only once, as multiple go dlls in the same program will confluct each other's go runtime at this time
* Unloading a dll will crash program... But one go dll loaded, and kept loaded, works..
* This may improve in the future as golang repairs these issues if they can.  
* A go runtime (which is included in all golang programs/code) is similar to a borland BPL or a .net runtime: multiple runtimes can be tricky/conflicting. It can even overwrite data if multiple runtimes exist, possibly even more tricky than a BPL. This again could be fixed in the future by golang authors if they work on dll's and unloading more in the future.
* regarding unix dll/so: I have not tested or read about it enough to know the details. This project is just a Microsoft Windows DLL project example, could also work on unix
* Go DLL, not "God II"
