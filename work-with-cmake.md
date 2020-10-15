## from http://derekmolloy.ie/hello-world-introductions-to-cmake

```cmake
cmake_minimum_required(VERSION version)
project(projectname)
```
Bring the headers into the project
`include_directories(includedir)`

Can manually add the sources using the set command as follows:
`set(SOURCES sth.cpp)`

However, the file(GLOB...) allows for wildcard additions:
`file(GLOB SOURCES "somepath/*.cpp")`

`add_executable(someexecutable ${SOURCES})`

Generate the shared library from the sources (other options are: STATIC or MODULE)
`add_library(somelib SHARED ${SOURCES})`
 
Set the location for library installation -- i.e., /usr/lib in this case not really necessary in this example. Use "sudo make install" to apply
`install(TARGETS installdir DESTINATION /usr/lib)`

use the ldd command to display the shared library dependencies
`ldd sth.so`

determine the constituents of a static library using the GNU ar (archive) command
`ar -t sth.a`

use the GNU nm command to list the symbols in object files and binaries
`nm -C sth.a`

use a library (static or shared)
```cmake
set ( PROJECT_LINK_LIBS somelib.so )
link_directories( libdir )
set ( PROJECT_LINK_LIBS somelib.a )
link_directories( libdir )
add_executable(execwithlink srcfile)
target_link_libraries(execwithlink ${PROJECT_LINK_LIBS} )
```
