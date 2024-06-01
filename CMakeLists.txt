cmake_minimum_required(VERSION 3.8)

PROJECT(dmsqlitepp)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
INCLUDE(cmake/ModuleImport.cmake)
INCLUDE(cmake/ModuleCompileOptions.cmake)
ModuleSetCompileOptions()
ModuleSetWinCompilerFlags()

ModuleImportAll("thirdparty")
LibImport("sqlite3" "src/sqlite3")

ExeImport("test" "sqlite3")
