cmake_minimum_required(VERSION 3.17)
project(secp256k1 C)

## run ./configure --with-bignum=no first
set(CMAKE_C_STANDARD 11)


include_directories(".")
include_directories("./src")
add_definitions(-DHAVE_CONFIG_H)
add_executable(bench_verify src/bench_verify.c src/secp256k1.c)
add_executable(bench_recover src/bench_recover.c src/secp256k1.c)

add_executable(bench_schnorrsig src/bench_schnorrsig.c src/secp256k1.c)
target_compile_definitions(bench_schnorrsig PRIVATE ENABLE_MODULE_SCHNORRSIG=1)
