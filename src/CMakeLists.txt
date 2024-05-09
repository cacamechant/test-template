set (srcs lib/app.c)
add_library(app MODULE ${srcs})

#add_subdirectory(tests)

install(TARGETS app
  LIBRARY DESTINATION ${CMAKE_INSTALL_PREFIX}/lib)

install(FILES ../app.json
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/share/app)

install(FILES www/index.html
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

install(FILES ../build/bundle.js
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

install(FILES www/main.css
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

install(FILES www/main.js
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

install(FILES www/fa-solid-900.eot
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

install(FILES www/fa-solid-900.ttf
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

install(FILES www/fa-solid-900.woff
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

install(FILES www/fa-solid-900.woff2
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

# install(DIRECTORY www/ 
#   DESTINATION ${CMAKE_INSTALL_PREFIX}/var/www/app)

install(DIRECTORY sql/ 
  DESTINATION ${CMAKE_INSTALL_PREFIX}/var/share/app/sql)
