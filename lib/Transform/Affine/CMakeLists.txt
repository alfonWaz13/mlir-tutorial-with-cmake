add_mlir_library(AffineFullUnrollPass
        AffineFullUnroll.cpp
        AffineFullUnroll.h
        LINK_LIBS PUBLIC
            MLIRIR
            MLIRPass
            MLIRAffineDialect
            MLIRTransforms
)