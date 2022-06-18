cmake_minimum_required(VERSION 3.11)

project(hardwaremonitor)

option(ENABLE_DEBUG "debug switch" ON)



file(GLOB harewaremonitor_SRC ${CMAKE_CURRENT_SOURCE_DIR}/OpenHarewareMonitorImp.cpp
                              ${CMAKE_CURRENT_SOURCE_DIR}/OpenHarewareMonitorImp.h
                              ${CMAKE_CURRENT_SOURCE_DIR}/UpdateVisitor.cpp
                              ${CMAKE_CURRENT_SOURCE_DIR}/UpdateVisitor.h
                              ${CMAKE_CURRENT_SOURCE_DIR}/app.rc)

add_library(hardwaremonitor SHARED ${harewaremonitor_SRC})


# c#library
add_library(LibreHardwareMonitorLib SHARED IMPORTED)

LIST(APPEND VS_DOTNET_REFERENCES "mscorlib")
LIST(APPEND VS_DOTNET_REFERENCES "System")
LIST(APPEND VS_DOTNET_REFERENCES "System.Xml")
LIST(APPEND VS_DOTNET_REFERENCES "System.Data")

set_target_properties(LibreHardwareMonitorLib PROPERTIES
    VS_DOTNET_REFERENCES "${VS_DOTNET_REFERENCES}"
    VS_DOTNET_REFERENCE_LibreHardwareMonitorLib "${CMAKE_CURRENT_SOURCE_DIR}/LibreHardwareMonitorLib.dll")

# set(CMAKE_CXXFLAGS_STL_ON /EHa)
# SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES COMPILE_FLAGS "/clr")
# STRING(REPLACE "/EHsc" "/EHa" CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS})
# STRING(REPLACE "/RTC1" "" CMAKE_CXX_FLAGS_DEBUG ${CMAKE_CXX_FLAGS_DEBUG})
# SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /clr")
# set_target_properties(${PROJECT_NAME} PROPERTIES COMMON_LANGUAGE_RUNTIME "${CMAKE_CURRENT_SOURCE_DIR}/LibreHardwareMonitorLib.dll")

target_compile_options(${PROJECT_NAME} PRIVATE /clr)
target_compile_options(${PROJECT_NAME} PRIVATE /fp:precise) # /fp:strict is

set_property(TARGET ${PROJECT_NAME} PROPERTY VS_GLOBAL_ROOTNAMESPACE ${project_name})
set_property(TARGET ${PROJECT_NAME} PROPERTY VS_GLOBAL_KEYWORD "ManagedCProj")
set_property(TARGET ${PROJECT_NAME} PROPERTY VS_GLOBAL_CLRSupport "true")
set_property(TARGET ${PROJECT_NAME} PROPERTY VS_DOTNET_TARGET_FRAMEWORK_VERSION "4.7.2")
set_property(TARGET ${PROJECT_NAME} PROPERTY VS_DOTNET_REFERENCES "System" "System.Data" "System.Drawing" "System.Windows.Forms" "System.Xml")

target_compile_definitions(${PROJECT_NAME} PRIVATE _UNICODE UNICODE)

# Note: Modification of compiler flags is required for CLR compatibility now that we are using .resx files.
string(REPLACE "/EHsc" "" CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}")
string(REPLACE "/RTC1" "" CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG}")

# STRING(REPLACE "/EHsc" "/EHa" CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS})
# STRING(REPLACE "/RTC1" "" CMAKE_CXX_FLAGS_DEBUG ${CMAKE_CXX_FLAGS_DEBUG})
# SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /clr")

# set_target_properties(LibreHardwareMonitorLib PROPERTIES IMPORTED_LOCATION "${CMAKE_CURRENT_SOURCE_DIR}/LibreHardwareMonitorLib.dll")

target_include_directories(hardwaremonitor PRIVATE ${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_SOURCE_DIR}/include)

target_link_libraries(hardwaremonitor PRIVATE LibreHardwareMonitorLib)