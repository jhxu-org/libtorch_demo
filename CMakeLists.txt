cmake_minimum_required(VERSION 3.7)
project(TESTCC)

set(CMAKE_CXX_STANDARD 11)
set(SOURCE_FILES main.cpp)
set(Torch_DIR L:\\libtorch-win-shared-with-deps-debug-latest\\libtorch\\share\\cmake\\Torch)
set(CUDA_DIR C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v10.0\\lib\\x64)
include_directories(L:\\libtorch-win-shared-with-deps-debug-latest\\libtorch\\include C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v10.0\\include)
link_directories(L:\\libtorch-win-shared-with-deps-debug-latest\\libtorch\\lib)
#find_library(${TORCH_LIBRARIES} L:\\libtorch-win-shared-with-deps-debug-latest\\libtorch\\share\\cmake\\Torch)
find_package(Torch REQUIRED)
find_package(CUDA REQUIRED)
add_executable(TESTCC ${SOURCE_FILES})
target_link_libraries(TESTCC ${TORCH_LIBRARIES})

