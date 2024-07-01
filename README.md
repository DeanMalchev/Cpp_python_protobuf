# Cpp_python_protobuf
This is a simple example of python/C++ communication using 
protobuf for serialization and UNIX sockets originally written by 
[Benoit Rosa](https://github.com/benoitrosa/Cpp_python_protobuf/). 
For client and server there are implementations in C++ and python. 

Cmake files and python code have been updated to work on Linux 
Arch (kernel 6.9.7-arch1-1). The only (obvious) dependency, aside 
of UNIX socket functions, is the [protobuf](https://protobuf.dev/) 
library.

In order to build the example, execute the following commands
(assuming your current directory is the repository's root):
```
    cmake -S . -B build 
    cmake --build build
```
The (C++) executables can be found in the `build` sub directory.
