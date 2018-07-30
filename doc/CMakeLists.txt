SET(DOXYFILE_IN ${CMAKE_CURRENT_SOURCE_DIR}/Doxyfile.in)
SET(DOXYFILE ${CMAKE_CURRENT_BINARY_DIR}/Doxyfile)
CONFIGURE_FILE(${DOXYFILE_IN} ${DOXYFILE} @ONLY)
FIND_PACKAGE(Doxygen)

ADD_CUSTOM_TARGET(doc
                  Doxygen::doxygen ${DOXYFILE}
                  WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
                  COMMENT "Generating API documentation with doxygen"
                  VERBATIM)
