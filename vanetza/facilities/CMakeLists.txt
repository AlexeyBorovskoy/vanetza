set(CXX_SOURCES
    cam_functions.cpp
    fixed_time_plan.cpp
    map_functions.cpp
    map_spat_validation.cpp
    path_history.cpp
    path_point.cpp
    priority_functions.cpp
    spat_functions.cpp
    validation.cpp
)

add_vanetza_component(facilities ${CXX_SOURCES})
target_link_libraries(facilities PUBLIC Boost::date_time asn1 security)
target_link_libraries(facilities PRIVATE geodesy)

add_test_subdirectory(tests)

