# -*- cmake -*-

SET(QT_USE_QTXML 1)
SET(QT_USE_QTUITOOLS 1)
#INCLUDE(${QT_USE_FILE})		     
INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}" "${CMAKE_CURRENT_BINARY_DIR}" "${Qt5Widgets_INCLUDE_DIRS}" "${Qt5UiTools_INCLUDE_DIRS}")

SET(qtuiloader_SRC uiloader.h uiloader.cpp)

MACRO_INSTALL_QTLUA_FILES(qtuiloader init.lua test.lua test.ui)

MACRO_ADD_QTLUA_MODULE(libqtuiloader ${qtuiloader_SRC})
TARGET_LINK_LIBRARIES(libqtuiloader ${Qt5UiTools_LIBRARIES})

#ADD_TORCH_DOK(dok qtuiloader "QT Interface" "QT Designer UI files loader" 6.)
