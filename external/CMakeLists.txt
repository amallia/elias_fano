EXECUTE_PROCESS(COMMAND git submodule update --init
                WORKING_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/..
                OUTPUT_QUIET
        )


add_subdirectory(bit_vector EXCLUDE_FROM_ALL)

if(NOT TARGET gtest)
add_subdirectory(googletest EXCLUDE_FROM_ALL)
endif()

if(NOT TARGET benchmark)
set(BENCHMARK_ENABLE_TESTING OFF CACHE BOOL "Suppressing benchmark's tests" FORCE)
add_subdirectory(benchmark EXCLUDE_FROM_ALL)
endif()