set(NAME vixl)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
add_definitions(-DVIXL_INCLUDE_TARGET_AARCH64=1)
add_definitions(-DVIXL_CODE_BUFFER_MMAP=1)
add_definitions(-DVIXL_INCLUDE_SIMULATOR_AARCH64=1)

if(CMAKE_BUILD_TYPE MATCHES DEBUG)
  add_definitions(-DVIXL_DEBUG=1)
endif()

set(SRCS
  code-buffer-vixl.cc
  compiler-intrinsics-vixl.cc
  cpu-features.cc
  utils-vixl.cc
  aarch64/assembler-aarch64.cc
  aarch64/cpu-aarch64.cc
  aarch64/cpu-features-auditor-aarch64.cc
  aarch64/decoder-aarch64.cc
  aarch64/disasm-aarch64.cc
  aarch64/instructions-aarch64.cc
  aarch64/logic-aarch64.cc
  aarch64/macro-assembler-aarch64.cc
  aarch64/operands-aarch64.cc
  aarch64/pointer-auth-aarch64.cc
  aarch64/simulator-aarch64.cc
  )
add_library(${NAME} STATIC ${SRCS})

