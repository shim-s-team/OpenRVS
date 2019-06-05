# CMakeList.txt : 최상위 CMake 프로젝트 파일, 전역 구성을 수행하고
# 여기에 하위 프로젝트를 포함합니다.
#
cmake_minimum_required (VERSION 3.8)

project ("Shims_Vision_Project")

# 하위 프로젝트를 포함합니다.
if(WIN32)
	add_subdirectory ("./Shims_Vision_Project/test_win")
elseif(APPLE)
	add_subdirectory ("./Shims_Vision_Project/test_apple")
else()
	message(FATAL_ERROR "No implementation for the platform")
endif()
