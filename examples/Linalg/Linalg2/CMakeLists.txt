add_subdirectory(lib)

set(LLVM_LINK_COMPONENTS
  Core
  Support
  )

set(LLVM_OPTIONAL_SOURCES Example.cpp)

add_llvm_example(linalg-example-2
  Example.cpp
  )

target_link_libraries(linalg-example-2
  PRIVATE
    MLIRAnalysis
    MLIRDialect
    MLIREDSC
    MLIRIR
    MLIRLLVMIR
    MLIRParser
    MLIRPass
    MLIRTransforms
    Linalg1
    Linalg2
    Linalg2DialectConstruction
    )

whole_archive_link(linalg-example-2
  MLIRStandardOps
  )
