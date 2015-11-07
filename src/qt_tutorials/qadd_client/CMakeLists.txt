##############################################################################
# Sections
##############################################################################

file(GLOB_RECURSE QT_MOC RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} FOLLOW_SYMLINKS *.hpp)
if (QT5)
QT5_WRAP_CPP(QT_MOC_HPP ${QT_MOC})
else (QT5)
QT4_WRAP_CPP(QT_MOC_HPP ${QT_MOC})
endif (QT5)

##############################################################################
# Sources
##############################################################################

file(GLOB_RECURSE QT_SOURCES RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} FOLLOW_SYMLINKS *.cpp)

##############################################################################
# Binaries
##############################################################################

add_executable(qadd_client ${QT_SOURCES} ${QT_MOC_HPP})
target_link_libraries(qadd_client qtutorials)
install(TARGETS qadd_client RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
