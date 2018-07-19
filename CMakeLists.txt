project(sqlparser)
cmake_minimum_required( VERSION 2.8.12 )

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(Src "${CMAKE_CURRENT_SOURCE_DIR}/src")
file(GLOB Parser_H "${Src}/*.h")
file(GLOB Parser_CPP "${Src}/*.cpp")
file(GLOB Sql_H "${Src}/sql/*.h")
file(GLOB Sql_CPP "${Src}/sql/*.cpp")
file(GLOB Util_H "${Src}/util/*.h")
file(GLOB Util_CPP "${Src}/util/*.cpp")


add_library(sqlparser STATIC
    ${Parser_H}
    ${Sql_H}
    ${Util_H}
   "${Src}/parser/bison_parser.h"
   "${Src}/parser/flex_lexer.h"
   ${Parser_CPP}
   ${Sql_CPP}
   ${Util_CPP}
   "${Src}/parser/bison_parser.cpp"
   "${Src}/parser/flex_lexer.cpp" 
)
