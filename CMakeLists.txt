add_definitions(-DSHOW_RESULTS)

if (NOT DEFINED DynamoRIO_DIR)
  set(DynamoRIO_DIR "../source/build/cmake" CACHE PATH
    "DynamoRIO installation's cmake directory")
endif (NOT DEFINED DynamoRIO_DIR)

find_package(DynamoRIO)
if (NOT DynamoRIO_FOUND)
  message(FATAL_ERROR "DynamoRIO package required to build")
endif(NOT DynamoRIO_FOUND)

add_library(inscount SHARED inscount.c)
configure_DynamoRIO_client(inscount)
use_DynamoRIO_extension(inscount drmgr)

add_library(myclient SHARED myclient.c)
configure_DynamoRIO_client(myclient)
use_DynamoRIO_extension(myclient drmgr)
