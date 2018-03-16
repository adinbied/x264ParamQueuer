# x264ParamQueuer
Automatically creates test encodes based on a given x264 encoding parameter

**NOTE:** This code is not my best work (was bodged together in under an hour), so it's not the prettiest or most elegant thing ever, but it gets the job done. 

## Overview
x264ParamQueuer takes the location of an AVS file, an output directory, and any other x264 settings you've already tested, and then it will move onto the next advanced encoding string and auto-encode a set of test encodes, varying the paramaters each time. It tests `QComp 0.60-0.80`, `AQ Modes 1,2, and 3`, `AQ Strength 0.50-1.10`, `Psy-RD 0.80-1.15`, and `Psy-Trellis 0.00-0.15`. The actual comparisons and determining optimal value still has to be done manually, but this should reduce time adding stuff to x264 Launcher's queue.

## Usage
To use, either clone the repo or just copy/paste ParamQueuer.bat into your text editor of choice, then save it as a batch file. Open it up and follow the prompts, and you should be good to go!

## Assumptions and Limitations
In no particular order, here are the assumptions made in order for this to work:
1. You are running a 64-bit version of Windows
2. You are using a recent version of Mulder's x264 Launcher, and have the associated files stored in `C:\Program Files (x86)\MuldeR\Simple x264 Launcher v2\toolset\x86\avs2yuv_x86.exe` and `C:\Program Files (x86)\MuldeR\Simple x264 Launcher v2\toolset\x64\x264_x64.exe`
3. You don't need to test CRF (assumes you've tested and have a 2-pass target bitrate already)
4. Other encoding parameters are hardcoded, so `--level 4.1 --subme 10 --deblock -3,-3 --me umh --merange 52 --rc-lookahead 250 --bframes 16 --no-mbtree `and` --trellis 2` cannot be tested in the current version.
5. You are using Avisynth (VapourSynth is not currently supported)
6. You don't need x264 .log files saved for every test encode

