project(dsdtest)

add_subdirectory(gtest)
add_subdirectory(gmock)

FILE(GLOB SRCS *.cpp ${dsd_SOURCE_DIR}/src/Hamming.cpp)

include_directories(
    ${PROJECT_SOURCE_DIR}/gtest/include
    ${PROJECT_SOURCE_DIR}/gmock/include
)

ADD_EXECUTABLE(dsdtest ${SRCS})
TARGET_LINK_LIBRARIES(dsdtest gmock gtest)

add_test(gtest dsdtest)
