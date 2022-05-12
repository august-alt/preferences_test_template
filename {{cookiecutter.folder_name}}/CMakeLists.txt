find_package(Qt5 COMPONENTS Core Gui Widgets Test REQUIRED)

find_package(XercesC REQUIRED)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)

set(HEADERS
    {{cookiecutter.widget_name|lower}}widgettest.h
)

set(SOURCES
    {{cookiecutter.widget_name|lower}}widgettest.cpp
)

set(SOURCES ${SOURCES} ${HEADERS})

add_executable({{cookiecutter.widget_name|lower}}widgettest ${SOURCES})
target_link_libraries({{cookiecutter.widget_name|lower}}widgettest Qt5::Core Qt5::Gui Qt5::Widgets Qt5::Test XercesC::XercesC)
add_preferences_editor_test(preferences.{{cookiecutter.widget_name|lower}}widgettest {{cookiecutter.widget_name|lower}}widgettest)

