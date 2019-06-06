# CMakeList.txt : 최상위 CMake 프로젝트 파일, 전역 구성을 수행하고
# 여기에 하위 프로젝트를 포함합니다.
#
cmake_minimum_required (VERSION 3.8)

project ("Shims_Vision_Project")

# 테스트 프로젝트의 포함여부를 결정합니다.
set(USE_TEST true)

# 라이브러리 생성 프로젝트의 포함여부를 결정합니다.
set(CREATE_LIBRARY true)

# 라이브러리 생성 프로젝트를 포함합니다.
if(CREATE_LIBRARY)
	# TODO: 생성할 라이브러리 프로젝트를 포함해야 합니다.
endif()

# 테스트 프로젝트를 포함합니다.
if (USE_TEST)
	if(WIN32)
		add_subdirectory ("./test/win")
	elseif(APPLE)
		add_subdirectory ("./test/apple")
	else()
		message(FATAL_ERROR "No implementation for the platform")
	endif()
endif()