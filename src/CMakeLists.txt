set(SRC_LIST lib.cpp)
set(HEADER_LIST ${PROJECT_SOURCE_DIR}/include/project_with_spdlog/lib.hpp)

add_library(project_with_spdlog ${SRC_LIST} ${HEADER_LIST})
target_include_directories(project_with_spdlog PUBLIC ${PROJECT_SOURCE_DIR}/include)
target_compile_features(project_with_spdlog PUBLIC cxx_std_17)
target_link_libraries(project_with_spdlog PRIVATE spdlog::spdlog)

install(TARGETS project_with_spdlog DESTINATION lib)
install(FILES ${HEADER_LIST} DESTINATION include/project_with_spdlog)