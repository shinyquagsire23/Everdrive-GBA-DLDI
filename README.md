# Everdrive-GBA-DLDI

This repository contains the code and `.dldi` patches for using the Everdrive-GBA X5 with libgba/libfat. In theory it might also work with libnds, but it is currently untested.

## Notes/TODO
 * ED_DLDI__startup could be improved to short-circuit if it can't detect an Everdrive
 * ED_DLDI__isInserted is unimplemented, however there's also not any reason hotplugging couldn't be supported?
 * ED_DLDI__clearStatus is unimplemented, not sure what a good implementation would look like (seems several DLDIs don't implement it...)
 * Sector read/write expects 4-byte aligned pointers due to using DMA Channel 3
 * Heuristics are still needed to detect CFG_RTC_ON, CFG_ROM_BANK, and CFG_BIG_ROM; RTC will be disabled when SD is initialized. 32 MiB ROMs might not work correctly.
