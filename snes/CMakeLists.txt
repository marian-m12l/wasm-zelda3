target_sources(zelda3 PRIVATE
    "apu.c"
    "apu.h"
    "cart.c"
    "cart.h"
    "cpu.c"
    "cpu.h"
    "dma.c"
    "dma.h"
    "dsp.c"
    "dsp.h"
    "dsp_regs.h"
    "input.c"
    "input.h"
    "ppu.c"
    "ppu.h"
    "saveload.h"
    "snes.c"
    "snes.h"
    "snes_other.c"
    "snes_regs.h"
    "spc.c"
    "spc.h"
    "tracing.c"
    "tracing.h"
)

if (WIN32)
    target_sources(zelda3 PRIVATE
        "platform/win32/volume_control.c"
        "platform/win32/volume_control.h"
    )
endif()

if (NINTENDO_SWITCH)
    target_include_directories(zelda3 PRIVATE "platform/switch/src")
    target_sources(zelda3 PRIVATE
        "platform/switch/src/switch_impl.c"
        "platform/switch/src/switch_impl.h"
    )
endif()
