###############################################################################
# Macro
###############################################################################

macro(ecl_utilities_add_gtest test_name)
  ament_add_gtest(ecl_test_${test_name} ${test_name}.cpp)
  # If we don't have gtest installed, then the target doesn't get made - check!
  if(TARGET ecl_test_${test_name})
      target_link_libraries(ecl_test_${test_name} ${PROJECT_NAME})
  endif()
endmacro()

###############################################################################
# Tests
###############################################################################

ecl_utilities_add_gtest(function_objects)
ecl_utilities_add_gtest(references)
ecl_utilities_add_gtest(singleton)
ecl_utilities_add_gtest(parameters)
ecl_utilities_add_gtest(flags)
