cmake_minimum_required(VERSION 3.21)

PROJECT(dmsqlitepp)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
INCLUDE(cmake/ModuleImport.cmake)
INCLUDE(cmake/ModuleCompileOptions.cmake)
ModuleSetCompileOptions()
ModuleSetWinCompilerFlags()

LibImport("sqlite3" "src/sqlite3")

if (PROJECT_IS_TOP_LEVEL)
	ExeImport("test" "sqlite3")
endif(PROJECT_IS_TOP_LEVEL)