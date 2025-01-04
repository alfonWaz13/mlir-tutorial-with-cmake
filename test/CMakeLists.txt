# Define las dependencias de las pruebas
set(MLIR_TEST_DEPENDS
        tutorial-opt # Herramienta que ejecuta el pase
)

add_lit_testsuite(check-affine-unroll "Running Affine Loop Unroll Tests"
        ${CMAKE_CURRENT_BINARY_DIR}
        DEPENDS ${MLIR_TEST_DEPENDS}
)

add_lit_testsuites(Affine ${CMAKE_CURRENT_SOURCE_DIR}
        DEPENDS ${MLIR_TEST_DEPENDS}
)
