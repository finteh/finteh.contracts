add_contract(finteh.token finteh.token ${CMAKE_CURRENT_SOURCE_DIR}/src/finteh.token.cpp)

target_include_directories(finteh.token
   PUBLIC
   ${CMAKE_CURRENT_SOURCE_DIR}/include)

set_target_properties(finteh.token
   PROPERTIES
   RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/ricardian/finteh.token.contracts.md.in ${CMAKE_CURRENT_BINARY_DIR}/ricardian/finteh.token.contracts.md @ONLY )

target_compile_options( finteh.token PUBLIC -R${CMAKE_CURRENT_SOURCE_DIR}/ricardian -R${CMAKE_CURRENT_BINARY_DIR}/ricardian )
