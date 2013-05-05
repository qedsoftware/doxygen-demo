Description
=============================================
Demonstration of using Doxygen to automatically generate documentation for C++ code.

Authoring credits go to Brent Nash who wrote this code for a Doxygen tutorial delivered at USC (http://merlot.usc.edu/cs102-s12/doxygen/).   

I only added CMake support and a README.

William Wu, 2013-03-25 22:41

Procedure for building code using CMake:
=============================================

	[doxygen-demo]$ mkdir build

	[doxygen-demo]$ cd build

	[doxygen-demo/build]$ cmake ..

	[doxygen-demo/build]$ make

Note that the last two commands are executed inside the build directory.

Afterwards, your tree structure should look like this:

	[doxygen-demo]$ tree -L 2
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

    [doxygen-demo/build/src]$ ./shape_demo

For more information on using CMake, check out http://www.cmake.org/cmake/help/cmake_tutorial.html


Procedure for constructing Doxygen documentation:
=============================================

	[doxygen-demo]$ cd src

	[doxygen-demo/src]$ doxygen Doxyfile

	[doxygen-demo/src]$ cd latex

	[doxygen-demo/src/latex]$ make

HTML documentation will then reside in doxygen-demo/src/html
LaTeX documentation will then reside at doxygen-demo/src/latex/refman.pdf

Pro tip: to launch an instant localhost HTTP server for viewing the HTML documentation, you can type:

    doxygen-demo/src/html]$ python -m SimpleHTTPServer

then go to http://localhost:8000/
