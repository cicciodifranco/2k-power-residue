cmake_minimum_required(VERSION 3.13)
project(2k_power_residue_symbols C)

set(CMAKE_C_STANDARD 99)


# Headers dir
include_directories(src/include)

# Tests
add_executable(
        2k-prs-test
        # sources

        # utils
        src/utils/lib-mesg.c
        src/utils/lib-timing.c
        src/utils/lib-misc.c

        # lib sources
        src/lib/lib-2k-prs.c
        src/tests/2k-prs.c)

# Main
add_executable(
        2k-prs
        # sources
        src/main.c

        # utils
        src/utils/lib-mesg.c
        src/utils/lib-timing.c
        src/utils/lib-misc.c

        # lib sources
        src/lib/lib-2k-prs.c)


# Linking libraries
# - GMP
# - Math
# - Pbc
target_link_libraries(2k-prs gmp m pbc)
target_link_libraries(2k-prs-test gmp m pbc)