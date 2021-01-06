cmake_minimum_required(VERSION 3.4)

include (AddStaticLibrary)
include (AddWin32DLL)

add_library(winsparkle INTERFACE)
#add_library(winsparkle_imported STATIC IMPORTED GLOBAL)
target_include_directories(winsparkle INTERFACE include)

add_static_library_to_interface(winsparkle build/winsparkle.lib)
add_win32_dll(winsparkle::dll build/winsparkle.dll)

#target_include_directories(winsparkle_imported INTERFACE include)
#set_target_properties(winsparkle_imported PROPERTIES
#    IMPORTED_LOCATION Release)
#target_link_library (winsparkle INTERFACE winsparkle_imported )
