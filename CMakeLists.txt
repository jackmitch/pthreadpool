cmake_minimum_required(VERSION 3.7)

include(GNUInstallDirs)

include_directories(include)
add_library(pthreadpool src/threadpool-pthreads.c)

set_target_properties(pthreadpool PROPERTIES PUBLIC_HEADER "include/pthreadpool.h")
target_compile_options(pthreadpool PUBLIC -fPIC)

install(TARGETS pthreadpool
	LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
	PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
	ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
)
