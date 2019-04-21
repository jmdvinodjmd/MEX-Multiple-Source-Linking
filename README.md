MEX compilation issue on Octave but works on MATLAB
====
I have multiple C++ files in a project. These compile perfectly on MATLAB but do not compile on Octave. There can be 'n' reasons for this problem but I am discussing one case which could lead to such situation.

Issue:
=======
In MATLAB you can specify multiple source files using '*.cpp' and that compiles properly but in Octave that does not seem to work and displays the following error:

Error: 
======
"clang: error: linker command failed with exit code 1 (use -v to see invocation)
warning: mkoctfile: building exited with failure status"

Solution:
==========
Simply specify all source files with their name and don't use '*' in compilation command.

Example: 
========
With problem:
mex -I.. -I./code -I./code1 -I./code2 main.cpp ./code1/*.cpp ./code2/*.cpp

With solution:
mex -I.. -I./code -I./code1 -I./code2 main.cpp ./code1/s1.cpp ./code2/s2.cpp
