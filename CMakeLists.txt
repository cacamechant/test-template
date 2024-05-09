cmake_minimum_required (VERSION 3.0)
project (pehu-app C)

set(CMAKE_INSTALL_PREFIX "/opt/pehu")
set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "gbe") #required
set(CPACK_DEBIAN_PACKAGE_DEPENDS "pehu-dev")

link_directories("/usr/local/unity")
include_directories("/usr/local/unity")


set(PostgreSQL_INCLUDE_DIRS "/usr/include/postgresql")
include_directories (${PostgreSQL_INCLUDE_DIRS})

find_program(MEMORYCHECK_COMMAND valgrind)
# set( MEMORYCHECK_COMMAND "/usr/bin/valgrind" )
set( MEMORYCHECK_COMMAND_OPTIONS "--trace-children=yes --leak-check=full --show-leak-kinds=all --track-origins=yes" )

include(CTest)
include(CPack)

include_directories(
  /opt/pehu/include
  )

link_directories(
  /opt/pehu/lib
  )


add_subdirectory(src)

