DynamoRio Client Practice
-------------------------
- CGO 2016 tutorial: https://github.com/DynamoRIO/dynamorio/releases/download/release_6_1_0/DynamoRIO-tutorial-mar2016.pdf
- DynamoRio Build Client: http://dynamorio.org/docs/using.html#sec_build
- api sample: http://dynamorio.org/docs/API_samples.htm

  - source code is in ``<build_dir>/api/sample``

- wiki: https://github.com/DynamoRIO/dynamorio/wiki/Downloads


practices
~~~~~~~~~
- myclient is sample in tutorial(CGO 2016)
- inscount is api sample

build it
~~~~~~~~
1. modify ``DynamoRIO_DIR`` in ``CMakeLists.txt``, assign to DynamoRio's ``<build_dir>/cmake`` directory.
2. build ::


   mkdir build/
   cd build/
   cmake -G "Unix Makefiles" ..
   make
   # target is build/libinscount.so, build/libmyclient.so
   
3. usage ::

   dyrun -c build/libinscount.so -- ls
   dyrun -c build/libmyclient.so -- ls
