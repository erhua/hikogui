# Copyright Take Vos 2021.
# Distributed under the Boost Software License, Version 1.0.
# (See accompanying file LICENSE_1_0.txt or copy at https://www.boost.org/LICENSE_1_0.txt)

target_sources(hikogui PRIVATE
    dither.hpp
    seed.hpp
    $<$<PLATFORM_ID:Windows>:${CMAKE_CURRENT_SOURCE_DIR}/seed_win32.cpp>
    xorshift128p.hpp
)

if(HI_BUILD_TESTS)
    target_sources(hikogui_tests PRIVATE
        dither_tests.cpp
        seed_tests.cpp
        xorshift128p_tests.cpp
    )
endif()

