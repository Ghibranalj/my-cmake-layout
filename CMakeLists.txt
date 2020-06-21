cmake_minimum_required(VERSION 3.7)

project (Helloer VERSION 1.0.0)


set (LIBRARIES "")

set(LIBS
## add subdirectories 
    static
    )

foreach(dir ${LIBS})
    add_subdirectory("${dir}")
endforeach()

## Set EXEC and link every libraries
add_executable(helloer main.cpp)
foreach(libs ${LIBRARIES})
    message(STATUS "linking library ${libs} to helloer")
    target_link_libraries(helloer PRIVATE ${libs})
endforeach()
