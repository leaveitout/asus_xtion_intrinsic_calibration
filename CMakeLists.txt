cmake_minimum_required(VERSION 3.3)
project(asus_xtion_intrinsic_calibration)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQIURED ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_HOME_DIRECTORY}/bin)

find_package(PCL 1.7 REQUIRED)
find_package(OpenCV REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

include_directories(${CMAKE_HOME_DIRECTORY}/include)

set(SOURCE_FILES src/main.cpp src/AsusXtionImageProducer.cpp include/AsusXtionImageProducer.h)

add_executable(asus_xtion_intrinsic_calibration ${SOURCE_FILES})

target_link_libraries(asus_xtion_intrinsic_calibration ${PCL_LIBRARIES})
target_link_libraries(asus_xtion_intrinsic_calibration ${OpenCV_LIBS})
