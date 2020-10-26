project(libssh-headers C)

set(libssh_HDRS
  callbacks.h
  libssh.h
  ssh2.h
  legacy.h
  libsshpp.hpp
)

if (WITH_SFTP)
  set(libssh_HDRS
    ${libssh_HDRS}
    sftp.h
  )
endif (WITH_SFTP)

if (WITH_SSH1)
  set(libssh_HDRS
    ${libssh_HDRS}
    ssh1.h
  )
endif (WITH_SSH1)

if (WITH_SERVER)
  set(libssh_HDRS
    ${libssh_HDRS}
    server.h
  )
endif (WITH_SERVER)

message(STATUS "Install headers: ... --> ${INCLUDE_INSTALL_DIR}/${APPLICATION_NAME} ")
install(
  FILES
    ${libssh_HDRS}
  DESTINATION
    ${INCLUDE_INSTALL_DIR}/${APPLICATION_NAME}
  COMPONENT
    headers
)

