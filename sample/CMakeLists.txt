cmake_minimum_required(VERSION 2.6)

option(BUILD_WXFREECHARTDEMO "Build wxfreechartdemo" ON)

if(WIN32)
  set(EXE_FLAG WIN32)
else(WIN32)
  set(EXE_FLAG "")
endif(WIN32)

IF(BUILD_WXFREECHARTDEMO)
  add_definitions("-D_LOCAL_")
  aux_source_directory( . DEMO_SRC )

  add_executable( wxfreechartdemo ${EXE_FLAG} ${DEMO_SRC} )
  target_link_libraries(wxfreechartdemo wxfreechart ${wxWidgets_LIBRARIES})
ENDIF()
