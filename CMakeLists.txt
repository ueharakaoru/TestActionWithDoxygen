cmake_minimum_required(VERSION 3.19)

project(test_action
    VERSION 1.0.0
    LANGUAGES CXX
)

# use C++ 17 standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# symbol visiblity
set(CMAKE_CXX_VISIBLIRY_PRESET hidden)
set(CMAKE_VISIBLITY_INLINES_HIDDEN TRUE)

find_package(Doxygen)

if (DOXYGEN_FOUND)
  set(DOXYGEN_GENERATE_TREEVIEW YES)
  set(DOXYGEN_DISABLE_INDEX NO)
  set(DOXYGEN_FULL_SIDEBAR NO)
  set(DOXYGEN_HTML_EXTRA_STYLESHEET doxygen-awesome.css)

  doxygen_add_docs(test_action__docs
    a.hpp
    mainpage.md
  )

endif()