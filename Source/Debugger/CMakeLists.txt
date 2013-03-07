# List the header files
set(HEADERS ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Debugger.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Debugger/Debugger.h
            ${LIBROCKET_SOURCE_DIR}/Include/Rocket/Debugger/Header.h
)

# List the source files
set(SRCS ${LIBROCKET_SOURCE_DIR}/Source/Debugger/BeaconSource.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/CommonSource.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/Debugger.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/ElementContextHook.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/ElementContextHook.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/ElementInfo.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/ElementInfo.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/ElementLog.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/ElementLog.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/FontSource.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/Geometry.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/Geometry.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/InfoSource.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/LogSource.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/MenuSource.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/Plugin.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/Plugin.h
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/SystemInterface.cpp
         ${LIBROCKET_SOURCE_DIR}/Source/Debugger/SystemInterface.h
)

# List the include paths
set(INCLUDE_PATHS "${LIBROCKET_SOURCE_DIR}/Include")

include_directories(${INCLUDE_PATHS})

# Declaration of the library
xmake_create_dynamic_library(ROCKETDEBUGGER RocketDebugger "1.2.2" "1.2.2" ${HEADERS} ${SRCS})

xmake_add_to_list_property(ROCKETDEBUGGER COMPILE_DEFINITIONS "RocketDebugger_EXPORTS")

xmake_project_link(ROCKETDEBUGGER ROCKETCORE)

# Exportations
xmake_export_include_paths(ROCKETDEBUGGER ${INCLUDE_PATHS})
