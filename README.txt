
Procedure for building code using CMake:
=============================================

[doxygen_shape_demo]$ mkdir build
[doxygen_shape_demo]$ cd build
[doxygen_shape_demo/build]$ cmake ..
[doxygen_shape_demo/build]$ make

Note that the last two commands are executed inside the build directory.

Afterwards, your tree structure should look like this:

[doxygen_shape_demo]$ tree -L 2
.
|-- CMakeLists.txt
|-- README.txt
|-- build
|   |-- CMakeCache.txt
|   |-- CMakeFiles
|   |-- Makefile
|   |-- cmake_install.cmake
|   |-- src
|-- src
    |-- CMakeLists.txt
    |-- main.cpp

and you can execute the program in the build/src directory as follows:

[doxygen_shape_demo/build/src]$ ./shape_demo

For more information on using CMake, check out http://www.cmake.org/cmake/help/cmake_tutorial.html


Procedure for constructing Doxygen documentation:
=============================================
[doxygen_shape_demo]$ cd src
[doxygen_shape_demo/src]$ doxygen Doxyfile
[doxygen_shape_demo/src]$ cd latex
[doxygen_shape_demo/src/latex]$ make

HTML documentation will reside in doxygen_shape_demo/src/html
LaTeX documentation at doxygen_shape_demo/src/latex/refman.pdf

Pro tip: to launch an instant localhost HTTP server for viewing the HTML documentation, you can type:

  [doxygen_shape_demo/src/html]$ python -m SimpleHTTPServer

then go to http://localhost:8000/

- William Wu, 2013-03-25 22:41
