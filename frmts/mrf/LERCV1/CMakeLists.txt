add_library(liblerc OBJECT Lerc1Image.cpp Lerc1Image.h)
target_include_directories(liblerc PRIVATE $<TARGET_PROPERTY:cpl,SOURCE_DIR> $<TARGET_PROPERTY:cpl,BINARY_DIR>)
set_property(TARGET liblerc PROPERTY POSITION_INDEPENDENT_CODE ${BUILD_SHARED_LIBS})
target_sources(${GDAL_LIB_TARGET_NAME} PRIVATE $<TARGET_OBJECTS:liblerc>)
target_compile_options(liblerc PRIVATE ${GDAL_CXX_WARNING_FLAGS})
