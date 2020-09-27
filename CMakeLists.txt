cmake_minimum_required(VERSION 3.17)
project(secp256k1 C)

# run firs:
#./configure --with-bignum=no --disable-tests
set(CMAKE_C_STANDARD 11)


include_directories(".")
include_directories("./src")
add_definitions(-DHAVE_CONFIG_H)
add_definitions(-DENABLE_MODULE_RECOVERY)
add_definitions(-DENABLE_MODULE_SCHNORRSIG)
add_definitions(-DENABLE_MODULE_EXTRAKEYS)

add_executable(bench_verify src/bench_verify.c src/secp256k1.c)

add_executable(bench_recover src/bench_recover.c src/secp256k1.c)

add_executable(bench_schnorrsig src/bench_schnorrsig.c src/secp256k1.c)
