get_property(dialect_libs GLOBAL PROPERTY MLIR_DIALECT_LIBS)
get_property(conversion_libs GLOBAL PROPERTY MLIR_CONVERSION_LIBS)
set(LIBS
        ${dialect_libs}
        ${conversion_libs}
        MLIROptLib
        MLIRPass
        AffineFullUnrollPass
)
add_llvm_executable(tutorial-opt tutorial-opt.cpp)

llvm_update_compile_flags(tutorial-opt)
target_link_libraries(tutorial-opt PRIVATE ${LIBS})
target_include_directories(tutorial-opt PRIVATE
        ${CMAKE_SOURCE_DIR}/lib
)
