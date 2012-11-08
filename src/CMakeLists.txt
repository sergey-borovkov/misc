find_package(Qt4 REQUIRED QtCore QtGui)
include(${QT_USE_FILE})


set(SOURCES main.cpp mainwindow.cpp)

set(FORMS mainwindow.ui)
qt4_wrap_ui(FORMS_HEADERS ${FORMS})

set(MOC_HEADERS mainwindow.h)
qt4_wrap_cpp(MOC_OUTFILES ${MOC_HEADERS})

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_BINARY_DIR})

add_executable(threads ${SOURCES} ${MOC_OUTFILES} ${FORMS_HEADERS})

target_link_libraries(threads ${QT_LIBRARIES})
