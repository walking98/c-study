1. build the lib so 
cmake  --build cmake-build-debug --target all

2. build test.cpp with the so
g++ test.cpp -Lcmake-build-debug -lmytestlib -o test

3. set shared lib
a) vi /etc/ld.so.conf
add the libmytestlib.so path into the config file & then, ldconfig to refresh the cache
or
b) export LD_LIBRARY_PATH=the paht

4. run test
./test



