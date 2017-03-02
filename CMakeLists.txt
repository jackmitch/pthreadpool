cmake_minimum_required(VERSION 3.7)

include(GNUInstallDirs)

include_directories(include)
add_library(pthreadpool src/pthreadpool.c)

install(TARGETS pthreadpool
	LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
	PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
	ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
)
