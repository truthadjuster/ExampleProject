cmake_minimum_required(VERSION 3.10)
project(ExampleProject)

set(CMAKE_CXX_STANDARD 14)

## file(GLOB APP_SOURCES */*.cpp)
## foreach (testsourcefile ${APP_SOURCES})	
##   get_filename_component(testname ${testsourcefile} NAME_WLE)	
##   get_filename_component(dirname ${testsourcefile} DIRECTORY)	
##   file(GLOB dir_src CONFIGURE_DEPENDS
## 	  "${dirname}/*.h"
## 	  "${dirname}/*.cpp"
## 	  )
##   message("${testname}.cpp | ${dir_src}")
## endforeach (testsourcefile ${APP_SOURCES})

###################################################
# As of cmake 3.1+, it is strongly discourage using 
# `file(GLOB` or `file(GLOB_RECURSE`

file(GLOB MYSOURCES my/*.h my/*.cpp my/dummy/*.cpp)
foreach(elemx ${MYSOURCES})
  message(STATUS "*** my ${elemx} ***")
endforeach()

include_directories(src)

add_subdirectory(src)
add_subdirectory(tst)
add_subdirectory(lib/googletest)
