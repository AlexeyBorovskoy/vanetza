include(UseGTest)

configure_gtest_directory(
    INCLUDE_DIRECTORIES ${CMAKE_CURRENT_SOURCE_DIR}/..
    LINK_LIBRARIES vanetza)
add_gtest(PriorityRequestTable priority_request_table.cpp ../priority_request_table.cpp)
add_gtest(ReferenceVectors reference_vectors.cpp ../reference_vectors.cpp ../fixed_time_intersection.cpp)
