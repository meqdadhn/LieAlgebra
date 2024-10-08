cmake_minimum_required(VERSION 3.12)
project(LieAlgebra)

# Set C++ standard
set(CMAKE_CXX_STANDARD 14)

# Find OpenCV 3.4
find_package(OpenCV 4.2.0 REQUIRED COMPONENTS core highgui imgproc features2d xfeatures2d)

# Include Eigen from the 3rdparty directory
include_directories(3rd_party/Eigen-3.3.7)

# Include Sophus from the 3rdparty directory
include_directories(3rd_party/Sophus)

# Set include directories
include_directories(include)

# Add your source files
add_executable(LieAlgebra src/main.cpp)

# Link against OpenCV 
target_link_libraries(LieAlgebra ${OpenCV_LIBS})
