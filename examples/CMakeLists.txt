
##################
# BUILD C EXAMPLES
##################

add_executable(test_libmeshb test_libmeshb.c)
target_link_libraries(test_libmeshb Meshb.7)
install (TARGETS test_libmeshb DESTINATION share/libMeshb/examples COMPONENT examples)

add_executable(test_libmeshb_block test_libmeshb_block.c)
target_link_libraries(test_libmeshb_block Meshb.7)
install (TARGETS test_libmeshb_block DESTINATION share/libMeshb/examples COMPONENT examples)

add_executable(test_libmeshb_sol test_libmeshb_sol.c)
target_link_libraries(test_libmeshb_sol Meshb.7)
install (TARGETS test_libmeshb_sol DESTINATION share/libMeshb/examples COMPONENT examples)


########################
# BUILD FORTRAN EXAMPLES
########################


if (CMAKE_Fortran_COMPILER)
   add_executable(test_libmeshb_f77 test_libmeshb.f)
   target_link_libraries(test_libmeshb_f77 Meshbf.7 gfortran)
   install (TARGETS test_libmeshb_f77 DESTINATION share/libMeshb/examples COMPONENT examples)

   add_executable(test_libmeshb_block_f77 test_libmeshb_block.f)
   target_link_libraries(test_libmeshb_block_f77 Meshbf.7 gfortran)
   install (TARGETS test_libmeshb_block_f77 DESTINATION share/libMeshb/examples COMPONENT examples)

   add_executable(test_libmeshb_block_pipeline test_libmeshb_block_pipeline.f)
   target_link_libraries(test_libmeshb_block_pipeline Meshbf.7 gfortran)
   install (TARGETS test_libmeshb_block_pipeline DESTINATION share/libMeshb/examples COMPONENT examples)
endif ()
