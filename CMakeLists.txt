cmake_minimum_required(VERSION 3.25)
project(Paralela)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fopenmp")

#Dependencias adicionales, me permite descargarlas
include(FetchContent)

FetchContent_Declare(
        fmt
        GIT_REPOSITORY https://github.com/fmtlib/fmt.git
        GIT_TAG 10.0.0
)

FetchContent_Declare(
        googletest
        GIT_REPOSITORY https://github.com/google/googletest.git
        GIT_TAG v1.13.0
)

FetchContent_Declare(
        benchmark
        GIT_REPOSITORY https://github.com/google/benchmark.git
        GIT_TAG v1.8.0
)

#para que este disponible para su uso en el proyecto actual
FetchContent_MakeAvailable(fmt googletest benchmark)


add_executable(Paralela main.cpp)

target_link_libraries(Paralela fmt::fmt benchmark::benchmark)

