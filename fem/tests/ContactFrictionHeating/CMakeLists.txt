INCLUDE(test_macros)
INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

CONFIGURE_FILE( case.sif case.sif COPYONLY)

file(COPY base.grd ELMERSOLVER_STARTINFO blunt.msh blunt.geo DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

ADD_ELMER_TEST(ContactFrictionHeating LABELS mortar elasticsolve limiter)
