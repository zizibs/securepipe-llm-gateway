add_library(security_analyzer STATIC
    SecurityAnalyzer.cpp
    SecurityAnalyzer.h
)

# Find required packages
find_package(Boost REQUIRED COMPONENTS regex)
find_package(Poppler REQUIRED)

# Link libraries
target_link_libraries(security_analyzer PRIVATE
    Boost::regex
    Poppler::Poppler
)

# Include directories
include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${Boost_INCLUDE_DIRS})
include_directories(${Poppler_INCLUDE_DIRS})