file(GLOB headers *.h)
add_executable(chapter_07 main.cpp ${headers})
# target_compile_options(chapter_07 PRIVATE -stdlib=libc++ -fexperimental-library)
target_link_libraries(chapter_07 PRIVATE pthread)