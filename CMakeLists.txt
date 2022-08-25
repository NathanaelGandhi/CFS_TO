cmake_minimum_required(VERSION 2.6.4)
project(TO C)

include_directories(fsw/mission_inc)
include_directories(fsw/platform_inc)
include_directories(fsw/src)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${ci_MISSION_DIR}/fsw/platform_inc)
include_directories(${ci_MISSION_DIR}/fsw/mission_inc)
include_directories(${ci_MISSION_DIR}/fsw/src)
include_directories(${io_lib_MISSION_DIR}/fsw/public_inc/)

include_directories(${MISSION_SOURCE_DIR}/apps/inc)
include_directories(${MISSION_SOURCE_DIR}/apps/cf/fsw/platform_inc)
include_directories(${MISSION_SOURCE_DIR}/apps/sch/fsw/platform_inc)
include_directories(${MISSION_SOURCE_DIR}/apps/hs/fsw/platform_inc)
include_directories(${MISSION_SOURCE_DIR}/apps/hk/fsw/platform_inc)

aux_source_directory(fsw/src APP_SRC_FILES)

# Create the app module
add_cfe_app(to ${APP_SRC_FILES})

    
include_directories(fsw/tables)

set(APP_TBL_FILES
  fsw/tables/to_config.c
  fsw/tables/to_config_2.c
)

add_cfe_tables(to fsw/tables/to_config.c)
