add_executable(fuzzing-persistent router_fuzzing_context.cpp persistent.cpp)
target_link_libraries(fuzzing-persistent PUBLIC vanetza)

add_executable(fuzzing-run router_fuzzing_context.cpp  run.cpp)
target_link_libraries(fuzzing-run PUBLIC vanetza)

add_executable(fuzzing-asn1 asn1_decoding.cpp asn1_persistent.cpp)
target_link_libraries(fuzzing-asn1 PUBLIC vanetza)

add_executable(fuzzing-asn1-run asn1_decoding.cpp asn1_run.cpp)
target_link_libraries(fuzzing-asn1-run PUBLIC vanetza)

option(FUZZ_WITH_LIBFUZZER "Build libFuzzer harness for infrastructure messages (Clang only)" OFF)
if(FUZZ_WITH_LIBFUZZER)
    add_executable(fuzzing-asn1-libfuzzer asn1_decoding.cpp asn1_libfuzzer.cpp)
    target_link_libraries(fuzzing-asn1-libfuzzer PUBLIC vanetza)
    target_compile_options(fuzzing-asn1-libfuzzer PRIVATE -fsanitize=fuzzer)
    target_link_options(fuzzing-asn1-libfuzzer PRIVATE -fsanitize=fuzzer)
endif()
