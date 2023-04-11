if (NOT WINDOWS_STORE AND NOT WINDOWS_PHONE)
  add_executable(t5 main.cpp)
  target_link_libraries(t5 cpprest)
endif()
