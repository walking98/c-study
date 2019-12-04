1. build the lib so 
cmake  --build cmake-build-debug --target all

2. build test.cpp with the so
g++ test.cpp -Lcmake-build-debug -lmytestlib -o cmake-build-debug/test

3. set shared lib
a) vi /etc/ld.so.conf
add the libmytestlib.so path into the config file & then, ldconfig to refresh the cache
or
b) export LD_LIBRARY_PATH=the paht

4. run test
./cmake-build-debug/test


5. flatpak-builder the lib
flatpak-builder --force-clean build  org.test.mytestlib.json

6. report the build(runtime/ext) into local flatpak(ostree) repository
flatpak build-export REPO-FULL-PATH build

7. install the runtime/ext
flatpak install REPO-REMOTE id

