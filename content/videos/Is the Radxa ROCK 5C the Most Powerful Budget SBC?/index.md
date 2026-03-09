---
title: "Is the Radxa ROCK 5C the Most Powerful Budget SBC?"
date: 2025-07-17
draft: false
summary: "This is my first post on my site"
tags: ["SBC", "Radxa", "Reviews"]
---
![alt text](featured.jpg)

In this video, I review Radxa's ROCK 5C, a powerful single-board computer powered by the 8-core Rockchip RK3588S2 SoC, featuring 4x Cortex-A76 and 4x Cortex-A55 cores.

Posted on YouTube: [https://youtu.be/R3_6UD4P_OY](https://youtu.be/R3_6UD4P_OY)

<img width="800" height="600" alt="IMG_4895" src="https://gist.github.com/user-attachments/assets/2052f002-65a6-4aff-ae2e-493b4b0cbb79" />



## Basic Information:

  - Board URL (official): [https://radxa.com/products/rock5/5c](https://radxa.com/products/rock5/5c)
  - Board purchased from: Sent for review from Radxa
  - Board purchase date: N/A
  - Board specs (as tested): 4GB RAM
  - Board price (as tested): $60.00

## Linux/System Information:

```
# output of `screenfetch`
         _,met$$$$$gg.           ryderhutchings@raspberrypi
      ,g$$$$$$$$$$$$$$$P.        OS: Debian 13 trixie
    ,g$$P""       """Y$$.".      Kernel: aarch64 Linux 6.12.47+rpt-rpi-2712
   ,$$P'              `$$$.      Uptime: 2h 9m
  ',$$P       ,ggs.     `$$b:    Packages: 1650
  `d$$'     ,$P"'   .    $$$     Shell: bash 5.2.37
   $$P      d$'     ,    $$P     Disk: 6.8G / 120G (6%)
   $$:      $$.   -    ,d$$'     CPU: ARM Cortex-A76 @ 4x 2.4GHz
   $$\;      Y$b._   _,d$P'      GPU: 
   Y$$.    `.`"Y$$$$P"'          RAM: 643MiB / 8047MiB
   `$$b      "-.__              
    `Y$$                        
     `Y$$.                      
       `$$b.                    
         `Y$$b.                 
            `"Y$b._             
                `""""           
                                
# output of `uname -a`
Linux raspberrypi 6.12.47+rpt-rpi-2712 #1 SMP PREEMPT Debian 1:6.12.47-1+rpt1 (2025-09-16) aarch64 GNU/Linux
```

## Benchmark Results:

### CPU

#### `Geekbench 6` results: 
- See: [https://browser.geekbench.com/v6/cpu/14915764](https://browser.geekbench.com/v6/cpu/12778048) and [https://browser.geekbench.com/v6/cpu/12806831](https://browser.geekbench.com/v6/cpu/12806831)

- 893 Single-Core Score / 2113 Multi-Core Score

#### `top500-benchmark` results:

- See: [geerlingguy/top500-benchmark](https://github.com/geerlingguy/top500-benchmark)

- 26.5 Gflops at 8.4–12.1 W, for 2.58 Gflops/W
<details>
<summary>Click to expand HPLinpack / top500-benchmark results</summary>

```
        ================================================================================
        HPLinpack 2.3  --  High-Performance Linpack benchmark  --   December 2, 2018
        Written by A. Petitet and R. Clint Whaley,  Innovative Computing Laboratory, UTK
        Modified by Piotr Luszczek, Innovative Computing Laboratory, UTK
        Modified by Julien Langou, University of Colorado Denver
        ================================================================================

        An explanation of the input/output parameters follows:
        T/V    : Wall time / encoded variant.
        N      : The order of the coefficient matrix A.
        NB     : The partitioning blocking factor.
        P      : The number of process rows.
        Q      : The number of process columns.
        Time   : Time in seconds to solve the linear system.
        Gflops : Rate of execution for solving the linear system.

        The following parameter values will be used:

        N      :   23314
        NB     :     256
        PMAP   : Row-major process mapping
        P      :       1
        Q      :       4
        PFACT  :   Right
        NBMIN  :       4
        NDIV   :       2
        RFACT  :   Crout
        BCAST  :  1ringM
        DEPTH  :       1
        SWAP   : Mix (threshold = 64)
        L1     : transposed form
        U      : transposed form
        EQUIL  : yes
        ALIGN  : 8 double precision words

        --------------------------------------------------------------------------------

        - The matrix A is randomly generated for each test.
        - The following scaled residual check will be computed:
              ||Ax-b||_oo / ( eps * ( || x ||_oo * || A ||_oo + || b ||_oo ) * N )
        - The relative machine precision (eps) is taken to be               1.110223e-16
        - Computational tests pass if scaled residuals are less than                16.0

        ================================================================================
        T/V                N    NB     P     Q               Time                 Gflops
        --------------------------------------------------------------------------------
        WR11C2R4       23314   256     1     4             318.89             2.6495e+01
        HPL_pdgesv() start time Mon Nov 17 01:58:00 2025

        HPL_pdgesv() end time   Mon Nov 17 02:03:19 2025

        --------------------------------------------------------------------------------
        ||Ax-b||_oo/(eps*(||A||_oo*||x||_oo+||b||_oo)*N)=   3.83945609e-03 ...... PASSED
        ================================================================================

        Finished      1 tests with the following results:
                      1 tests completed and passed residual checks,
                      0 tests completed and failed residual checks,
                      0 tests skipped because of illegal input values.
        --------------------------------------------------------------------------------

        End of Tests.
        ================================================================================
```
</details>

#### `sysbench` results:
- See: [akopytov/sysbench](https://github.com/akopytov/sysbench)

```
CPU speed:
    events per second:  4051.04

General statistics:
    total time:                          10.0008s
    total number of events:              40518

Latency (ms):
         min:                                    0.98
         avg:                                    0.99
         max:                                    4.99
         95th percentile:                        0.99
         sum:                                39991.52

Threads fairness:
    events (avg/stddev):           10129.5000/15.58
    execution time (avg/stddev):   9.9979/0.00
```
[comment]: # (sysbench cpu --cpu-max-prime=20000 --threads=4 run)

### Thermals
- See: [ryderhutchings/rk-thermal.sh](https://github.com/ryderhutchings/rk-thermal.sh)

| Test Condition      | With Heatsink (°C) | Without Heatsink (°C) | Notes |
|---------------------|--------------------|-------------------------|-------|
| Idle                 | TODO                    |  TODO                       | N/A |
| 1080p Playback       | TODO                    |   TODO                      | N/A |
| 4K Playback          | TODO                    |   TODO                      | N/A |
| Web Browsing         |   TODO                  |   TODO                      | N/A |
| FFmpeg Encoding      | TODO                    |   TODO                      | N/A |
| stress-ng (--cpu 4)  | TODO                   |  TODO                | N/A |
| sbc-bench Run        | TODO                   | TODO                 | N/A |
| **Peak Temperature** |   TODO                 |     TODO                   | N/A |


### Power

  - Idle shutdown power draw (at wall): TODO W
  - Idle power draw (at wall): 4.4 W to 5.3 W
  - Maximum simulated power draw (`stress-ng --matrix 0`): 8.3 W to 11.3 W
  - During Geekbench single-core benchmark: TODO W to TODO W
  - During Geekbench multi-core benchmark: TODO W to TODO W
  - During `top500` HPL benchmark: 8.4 W to 12.1 W

### Disk

#### External microSD (USD00-128GB)

[comment]: # (Run `lsblk -o NAME,FSTYPE,LABEL,MOUNTPOINT,SIZE,MODEL` to get model)

| Benchmark                  | Result |
| -------------------------- | ------ |
| iozone 4K random read      | 23.4 MB/s |
| iozone 4K random write     | 3.5 MB/s |
| iozone 1M random read      | 92.4 MB/s |
| iozone 1M random write     | 72.5 MB/s |
| iozone 1M sequential read  | 92.3 MB/s |
| iozone 1M sequential write | 72.5 MB/s |

### Network

> Note: All measurements were taken over Wi-Fi, not wired Ethernet.

`iperf3` results:

  - `iperf3 -c $SERVER_IP`: 221 Mbps
  - `iperf3 -c $SERVER_IP --reverse`: 135 Mbps
  - `iperf3 -c $SERVER_IP --bidir`: 38 Mbps up, 197 Mbps down

`nuttcp` results:

  - `nuttcp -t $SERVER_IP`: 315.7 MB /  10.07 sec =  262.9 Mbps

### GPU

`glmark2-es2` / `glmark2-es2-wayland` results:

```
=======================================================
    glmark2 2023.01
=======================================================
    OpenGL Information
    GL_VENDOR:      Broadcom
    GL_RENDERER:    V3D 7.1.7.0
    GL_VERSION:     OpenGL ES 3.1 Mesa 25.0.7-2+rpt2
    Surface Config: buf=32 r=8 g=8 b=8 a=8 depth=24 stencil=0 samples=0
    Surface Size:   800x600 windowed
=======================================================
[build] use-vbo=false: FPS: 2420 FrameTime: 0.413 ms
[build] use-vbo=true: FPS: 3053 FrameTime: 0.328 ms
[texture] texture-filter=nearest: FPS: 2320 FrameTime: 0.431 ms
[texture] texture-filter=linear: FPS: 2300 FrameTime: 0.435 ms
[texture] texture-filter=mipmap: FPS: 2386 FrameTime: 0.419 ms
[shading] shading=gouraud: FPS: 2511 FrameTime: 0.398 ms
[shading] shading=blinn-phong-inf: FPS: 2447 FrameTime: 0.409 ms
[shading] shading=phong: FPS: 2100 FrameTime: 0.476 ms
[shading] shading=cel: FPS: 2075 FrameTime: 0.482 ms
[bump] bump-render=high-poly: FPS: 1231 FrameTime: 0.813 ms
[bump] bump-render=normals: FPS: 2695 FrameTime: 0.371 ms
[bump] bump-render=height: FPS: 2490 FrameTime: 0.402 ms
[effect2d] kernel=0,1,0;1,-4,1;0,1,0;: FPS: 1014 FrameTime: 0.987 ms
[effect2d] kernel=1,1,1,1,1;1,1,1,1,1;1,1,1,1,1;: FPS: 393 FrameTime: 2.548 ms
[pulsar] light=false:quads=5:texture=false: FPS: 2525 FrameTime: 0.396 ms
[desktop] blur-radius=5:effect=blur:passes=1:separable=true:windows=4: FPS: 242 FrameTime: 4.138 ms
[desktop] effect=shadow:windows=4: FPS: 886 FrameTime: 1.129 ms
[buffer] columns=200:interleave=false:update-dispersion=0.9:update-fraction=0.5:update-method=map: FPS: 420 FrameTime: 2.383 ms
[buffer] columns=200:interleave=false:update-dispersion=0.9:update-fraction=0.5:update-method=subdata: FPS: 423 FrameTime: 2.368 ms
[buffer] columns=200:interleave=true:update-dispersion=0.9:update-fraction=0.5:update-method=map: FPS: 467 FrameTime: 2.142 ms
[ideas] speed=duration: FPS: 1864 FrameTime: 0.537 ms
[jellyfish] <default>: FPS: 1167 FrameTime: 0.857 ms
[terrain] <default>: FPS: 68 FrameTime: 14.781 ms
[shadow] <default>: FPS: 294 FrameTime: 3.405 ms
[refract] <default>: FPS: 97 FrameTime: 10.357 ms
[conditionals] fragment-steps=0:vertex-steps=0: FPS: 2834 FrameTime: 0.353 ms
[conditionals] fragment-steps=5:vertex-steps=0: FPS: 2166 FrameTime: 0.462 ms
[conditionals] fragment-steps=0:vertex-steps=5: FPS: 2803 FrameTime: 0.357 ms
[function] fragment-complexity=low:fragment-steps=5: FPS: 2514 FrameTime: 0.398 ms
[function] fragment-complexity=medium:fragment-steps=5: FPS: 1852 FrameTime: 0.540 ms
[loop] fragment-loop=false:fragment-steps=5:vertex-steps=5: FPS: 2416 FrameTime: 0.414 ms
[loop] fragment-steps=5:fragment-uniform=false:vertex-steps=5: FPS: 2420 FrameTime: 0.413 ms
[loop] fragment-steps=5:fragment-uniform=true:vertex-steps=5: FPS: 1761 FrameTime: 0.568 ms
=======================================================
                                  glmark2 Score: 1715 
=======================================================
```

### vkmark

`vkmark` results:
```
=======================================================
    vkmark 2025.01
=======================================================
    Vendor ID:      0x14E4
    Device ID:      0x55701C33
    Device Name:    V3D 7.1.7.0
    Driver Version: 104857607
    Device UUID:    b50fa0c9546221c07ec2a8ac7bf235fd
=======================================================
[vertex] device-local=true: FPS: 1803 FrameTime: 0.555 ms
[vertex] device-local=false: FPS: 1811 FrameTime: 0.552 ms
[texture] anisotropy=0: FPS: 1658 FrameTime: 0.603 ms
[texture] anisotropy=16: FPS: 1611 FrameTime: 0.621 ms
[shading] shading=gouraud: FPS: 1502 FrameTime: 0.666 ms
[shading] shading=blinn-phong-inf: FPS: 1473 FrameTime: 0.679 ms
[shading] shading=phong: FPS: 1315 FrameTime: 0.760 ms
[shading] shading=cel: FPS: 1324 FrameTime: 0.755 ms
[effect2d] kernel=edge: FPS: 889 FrameTime: 1.125 ms
[effect2d] kernel=blur: FPS: 377 FrameTime: 2.653 ms
[desktop] <default>: FPS: 762 FrameTime: 1.312 ms
[cube] <default>: FPS: 2122 FrameTime: 0.471 ms
[clear] <default>: FPS: 2355 FrameTime: 0.425 ms
=======================================================
                                   vkmark Score: 1461
=======================================================
```

## AI / LLM Inference:

Basic `ollama` LLM model inference results:

Running benchmark 3 times using model: `tinyllama:1.1b`
| Run | Eval Rate (Tokens/Second) |
|-----|-----------------------------|
| 1 | 17.17 tokens/s |
| 2 | 16.23 tokens/s |
| 3 | 16.66 tokens/s |
|**Average Eval Rate**| 16.68 tokens/second |

Running benchmark 3 times using model: `deepseek-r1:1.5b`
| Run | Eval Rate (Tokens/Second) |
|-----|-----------------------------|
| 1 | 11.44 tokens/s |
| 2 | 11.27 tokens/s |
| 3 | 11.47 tokens/s |
|**Average Eval Rate**| 11.39 tokens/second |

Running benchmark 3 times using model: `llama3.2:3b`
| Run | Eval Rate (Tokens/Second) |
|-----|-----------------------------|
| 1 | 3.79 tokens/s |
| 2 | 4.67 tokens/s |
| 3 | 5.00 tokens/s |
|**Average Eval Rate**| 4.48 tokens/second |

System used around 10.5 W during inference.

[comment]: # (Note that Ollama will run on the CPU if no valid GPU / drivers are present. Be sure to note whether Ollama runs on the CPU, GPU, or a dedicated NPU.)

## Memory:

### `tinymembench` results:

See: [rojaster/tinymembench](https://github.com/rojaster/tinymembench)

<details>
<summary>Click to expand tinymembench benchmark results</summary>

```
tinymembench v0.4.10 (simple benchmark for memory throughput and latency)

==========================================================================
== Memory bandwidth tests                                               ==
==                                                                      ==
== Note 1: 1MB = 1000000 bytes                                          ==
== Note 2: Results for 'copy' tests show how many bytes can be          ==
==         copied per second (adding together read and writen           ==
==         bytes would have provided twice higher numbers)              ==
== Note 3: 2-pass copy means that we are using a small temporary buffer ==
==         to first fetch data into it, and only then write it to the   ==
==         destination (source -> L1 cache, L1 cache -> destination)    ==
== Note 4: If sample standard deviation exceeds 0.1%, it is shown in    ==
==         brackets                                                     ==
==========================================================================

 C copy backwards                                     :   6060.4 MB/s (0.9%)
 C copy backwards (32 byte blocks)                    :   6031.6 MB/s (1.2%)
 C copy backwards (64 byte blocks)                    :   5977.7 MB/s (0.6%)
 C copy                                               :   5864.1 MB/s (1.7%)
 C copy prefetched (32 bytes step)                    :   5866.0 MB/s (1.3%)
 C copy prefetched (64 bytes step)                    :   5866.1 MB/s (1.2%)
 C 2-pass copy                                        :   5608.9 MB/s (0.7%)
 C 2-pass copy prefetched (32 bytes step)             :   5871.5 MB/s (0.9%)
 C 2-pass copy prefetched (64 bytes step)             :   5903.3 MB/s (0.8%)
 C fill                                               :   8797.3 MB/s (1.1%)
 C fill (shuffle within 16 byte blocks)               :   8822.8 MB/s (1.9%)
 C fill (shuffle within 32 byte blocks)               :   8836.7 MB/s (2.4%)
 C fill (shuffle within 64 byte blocks)               :   8802.1 MB/s (1.3%)
 NEON 64x2 COPY                                       :   5837.7 MB/s (0.5%)
 NEON 64x2x4 COPY                                     :   5816.3 MB/s (0.4%)
 NEON 64x1x4_x2 COPY                                  :   5811.9 MB/s (0.4%)
 NEON 64x2 COPY prefetch x2                           :   5653.4 MB/s (0.3%)
 NEON 64x2x4 COPY prefetch x1                         :   5751.7 MB/s (0.3%)
 NEON 64x2 COPY prefetch x1                           :   5647.2 MB/s (0.5%)
 NEON 64x2x4 COPY prefetch x1                         :   5751.2 MB/s (0.5%)
 ---
 standard memcpy                                      :   5862.7 MB/s (0.7%)
 standard memset                                      :   8817.8 MB/s (0.7%)
 ---
 NEON LDP/STP copy                                    :   5852.1 MB/s (1.1%)
 NEON LDP/STP copy pldl2strm (32 bytes step)          :   6011.3 MB/s (1.1%)
 NEON LDP/STP copy pldl2strm (64 bytes step)          :   5983.4 MB/s (0.8%)
 NEON LDP/STP copy pldl1keep (32 bytes step)          :   6010.9 MB/s (1.2%)
 NEON LDP/STP copy pldl1keep (64 bytes step)          :   6012.0 MB/s (0.9%)
 NEON LD1/ST1 copy                                    :   5859.7 MB/s (0.9%)
 NEON STP fill                                        :   8827.1 MB/s (6.1%)
 NEON STNP fill                                       :   8870.3 MB/s (1.5%)
 ARM LDP/STP copy                                     :   5799.5 MB/s (0.2%)
 ARM STP fill                                         :   8777.7 MB/s (3.0%)
 ARM STNP fill                                        :   8776.9 MB/s (3.4%)

==========================================================================
== Framebuffer read tests.                                              ==
==                                                                      ==
== Many ARM devices use a part of the system memory as the framebuffer, ==
== typically mapped as uncached but with write-combining enabled.       ==
== Writes to such framebuffers are quite fast, but reads are much       ==
== slower and very sensitive to the alignment and the selection of      ==
== CPU instructions which are used for accessing memory.                ==
==                                                                      ==
== Many x86 systems allocate the framebuffer in the GPU memory,         ==
== accessible for the CPU via a relatively slow PCI-E bus. Moreover,    ==
== PCI-E is asymmetric and handles reads a lot worse than writes.       ==
==                                                                      ==
== If uncached framebuffer reads are reasonably fast (at least 100 MB/s ==
== or preferably >300 MB/s), then using the shadow framebuffer layer    ==
== is not necessary in Xorg DDX drivers, resulting in a nice overall    ==
== performance improvement. For example, the xf86-video-fbturbo DDX     ==
== uses this trick.                                                     ==
==========================================================================

 NEON LDP/STP copy (from framebuffer)                 :   1620.3 MB/s (0.5%)
 NEON LDP/STP 2-pass copy (from framebuffer)          :   1457.2 MB/s (0.4%)
 NEON LD1/ST1 copy (from framebuffer)                 :   1633.0 MB/s (0.4%)
 NEON LD1/ST1 2-pass copy (from framebuffer)          :   1462.1 MB/s (0.2%)
 ARM LDP/STP copy (from framebuffer)                  :   1638.1 MB/s (0.6%)
 ARM LDP/STP 2-pass copy (from framebuffer)           :   1476.1 MB/s (0.7%)

==========================================================================
== Memory latency test                                                  ==
==                                                                      ==
== Average time is measured for random memory accesses in the buffers   ==
== of different sizes. The larger is the buffer, the more significant   ==
== are relative contributions of TLB, L1/L2 cache misses and SDRAM      ==
== accesses. For extremely large buffer sizes we are expecting to see   ==
== page table walk with several requests to SDRAM for almost every      ==
== memory access (though 64MiB is not nearly large enough to experience ==
== this effect to its fullest).                                         ==
==                                                                      ==
== Note 1: All the numbers are representing extra time, which needs to  ==
==         be added to L1 cache latency. The cycle timings for L1 cache ==
==         latency can be usually found in the processor documentation. ==
== Note 2: Dual random read means that we are simultaneously performing ==
==         two independent memory accesses at a time. In the case if    ==
==         the memory subsystem can't handle multiple outstanding       ==
==         requests, dual random read has the same timings as two       ==
==         single reads performed one after another.                    ==
==========================================================================

block size : single random read / dual random read
      1024 :    0.0 ns          /     0.0 ns 
      2048 :    0.0 ns          /     0.0 ns 
      4096 :    0.0 ns          /     0.0 ns 
      8192 :    0.0 ns          /     0.0 ns 
     16384 :    0.0 ns          /     0.0 ns 
     32768 :    0.0 ns          /     0.0 ns 
     65536 :    0.0 ns          /     0.0 ns 
    131072 :    1.1 ns          /     1.5 ns 
    262144 :    1.6 ns          /     2.0 ns 
    524288 :    1.9 ns          /     2.2 ns 
   1048576 :    8.4 ns          /    11.3 ns 
   2097152 :   13.4 ns          /    15.0 ns 
   4194304 :   50.4 ns          /    74.4 ns 
   8388608 :   78.0 ns          /   103.2 ns 
  16777216 :   92.1 ns          /   112.7 ns 
  33554432 :   99.9 ns          /   115.1 ns 
  67108864 :  104.6 ns          /   118.4 ns 
```
</details>

<img width="800" height="600" alt="tinymembench" src="https://gist.github.com/user-attachments/assets/d9df10d2-cc5e-4ab9-8418-65f6fabf4d32" />


### `c2clat` results:
See: [rigtorp/c2clat](https://github.com/rigtorp/c2clat):

Core-to-core memory latency across the CPU.

[comment]: # (If this is a new CPU/SoC, run c2clat to generate a core to core memory access latency graph: https://gist.github.com/geerlingguy/842974c0e49c201c28f4be54a05cc89c)

<img width="800" height="600" alt="c2clat(added name)" src="https://gist.github.com/user-attachments/assets/d4b39a6a-1094-4078-b3f5-13f5441a1f83" />





### `sbc-bench` results:
See: [ThomasKaiser/sbc-bench](https://github.com/ThomasKaiser/sbc-bench): 

```
  * cpu0 (Cortex-A76): memcpy: 5833.3 MB/s, memchr: 14175.7 MB/s, memset: 8793.9 MB/s
  * cpu0 (Cortex-A76): memcpy: 5595.0 MB/s, memchr: 13557.7 MB/s, memset: 8398.5 MB/s
  * cpu0 (Cortex-A76): memcpy: 5610.2 MB/s, memchr: 12562.5 MB/s, memset: 8393.7 MB/s
  * cpu0 (Cortex-A76): memcpy: 5604.5 MB/s, memchr: 12071.8 MB/s, memset: 8158.3 MB/s
  * cpu0 (Cortex-A76): memcpy: 5583.0 MB/s, memchr: 11777.0 MB/s, memset: 7997.3 MB/s
  * cpu0 (Cortex-A76): memcpy: 5599.3 MB/s, memchr: 11396.6 MB/s, memset: 8037.3 MB/s
  * cpu0 (Cortex-A76): memcpy: 5584.6 MB/s, memchr: 11045.0 MB/s, memset: 8253.4 MB/s
  * cpu0 (Cortex-A76): memcpy: 5609.0 MB/s, memchr: 11240.9 MB/s, memset: 7811.1 MB/s
  * cpu0 (Cortex-A76) 16M latency: 109.7 109.2 110.7 107.3 107.4 113.2 148.7 197.1
  * cpu0 (Cortex-A76) 16M latency: 109.9 109.8 105.9 105.7 107.7 116.7 147.1 201.0
  * cpu0 (Cortex-A76) 16M latency: 107.5 110.3 105.8 106.1 109.5 112.1 148.4 195.0
  * cpu0 (Cortex-A76) 16M latency: 109.4 106.3 109.9 109.9 107.7 111.7 146.7 201.0
  * cpu0 (Cortex-A76) 16M latency: 112.5 110.7 105.0 106.0 106.1 114.4 148.3 201.2
  * cpu0 (Cortex-A76) 16M latency: 109.6 106.4 104.8 110.4 110.5 112.9 147.5 202.3
  * cpu0 (Cortex-A76) 16M latency: 108.2 106.2 109.2 107.4 107.7 111.8 149.6 201.7
  * cpu0 (Cortex-A76) 16M latency: 110.6 108.7 108.0 106.4 110.0 113.0 146.0 197.8
  * cpu0 (Cortex-A76) 128M latency: 123.8 121.3 123.4 122.0 124.2 121.6 122.6 131.1
  * cpu0 (Cortex-A76) 128M latency: 122.4 121.1 123.0 121.5 121.9 120.7 123.1 128.0
  * cpu0 (Cortex-A76) 128M latency: 122.7 122.5 121.1 121.3 123.8 122.0 122.7 131.0
  * cpu0 (Cortex-A76) 128M latency: 122.7 122.4 121.8 122.5 122.2 120.9 123.6 130.3
  * cpu0 (Cortex-A76) 128M latency: 122.1 121.3 123.2 127.0 122.8 122.5 123.6 131.9
  * cpu0 (Cortex-A76) 128M latency: 122.4 123.4 122.4 121.5 121.7 121.6 124.6 130.1
  * cpu0 (Cortex-A76) 128M latency: 123.1 122.9 122.4 123.1 121.9 119.8 122.3 130.0
  * cpu0 (Cortex-A76) 128M latency: 121.5 121.2 123.1 120.4 122.1 123.3 122.8 128.8
  * 7-zip MIPS (3 consecutive runs): 7940, 7884, 7853 (7890 avg), single-threaded: 2890
  * aes-256-cbc     508247.02k   888119.32k  1132989.35k  1170084.86k  1194030.42k  1219067.90k (Cortex-A76)
  * aes-256-cbc     459408.67k   897897.73k  1055599.70k  1196050.09k  1157909.16k  1221984.26k (Cortex-A76)
  * aes-256-cbc     477768.62k   866586.60k  1086353.24k  1144383.83k  1173211.82k  1178501.12k (Cortex-A76)
  * aes-256-cbc     483928.96k   845066.09k  1095326.21k  1150651.39k  1183817.73k  1210231.47k (Cortex-A76)
  * aes-256-cbc     468158.78k   879290.67k  1055410.09k  1155632.47k  1136997.72k  1174765.57k (Cortex-A76)
  * aes-256-cbc     471090.47k   876449.43k  1036192.94k  1134801.92k  1192716.97k  1193033.73k (Cortex-A76)
  * aes-256-cbc     452475.42k   879628.48k  1102630.91k  1082959.87k  1168313.00k  1188173.14k (Cortex-A76)
  * aes-256-cbc     467721.51k   840143.21k  1064928.85k  1125768.87k  1186747.73k  1158518.10k (Cortex-A76)

```

<details>
<summary>Click to expand sbc-bench benchmark results</summary>

# Raspberry Pi 5 Model B Rev 1.0

Tested with sbc-bench v0.9.72 on Mon, 17 Nov 2025 05:14:19 +0000.

### General information:

    Information courtesy of cpufetch:
    
    SoC:                 Broadcom BCM2712
    Technology:          16nm
    Microarchitecture:   Cortex-A76
    Max Frequency:       2.400 GHz
    Cores:               4 cores
    Features:            NEON,SHA1,SHA2,AES,CRC32
    
The CPU features 8 clusters of same core type:

    BCM2712, Kernel: aarch64, Userland: arm64
    
    CPU sysfs topology (clusters, cpufreq members, clockspeeds)
                     cpufreq   min    max
     CPU    cluster  policy   speed  speed   core type
      0        0        0     1500    2400   Cortex-A76 / r4p1
      1        0        0     1500    2400   Cortex-A76 / r4p1
      2        0        0     1500    2400   Cortex-A76 / r4p1
      3        0        0     1500    2400   Cortex-A76 / r4p1

8059 KB available RAM

### Governors/policies (performance vs. idle consumption):

Original governor settings:

    cpufreq-policy0: performance / 2400 MHz (conservative ondemand userspace powersave performance schedutil / 1500 1600 1700 1800 1900 2000 2100 2200 2300 2400)

Tuned governor settings:

    cpufreq-policy0: performance / 2400 MHz

Status of performance related policies found below /sys:

    /sys/module/pcie_aspm/parameters/policy: default [performance] powersave powersupersave

### Clockspeeds (idle vs. heated up):

Before at 55.1°C:

    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2400, Measured: 2398 
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2400, Measured: 2399 
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2400, Measured: 2399 
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2400, Measured: 2399 
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2400, Measured: 2398 
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2400, Measured: 2399 
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2400, Measured: 2398 
    cpu0-cpu3 (Cortex-A76): OPP: 2400, ThreadX: 2400, Measured: 2399 

After at 88.1°C (throttled):

    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 1500, Measured: 1954     (-18.6%)
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2256, Measured: 2184      (-9.0%)
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2311, Measured: 2224      (-7.3%)
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2256, Measured: 2263      (-5.7%)
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2146, Measured: 2261      (-5.8%)
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 1500, Measured: 2240      (-6.7%)
    cpu0-cpu-1 (Cortex-A76): OPP: 2400, ThreadX: 2146, Measured: 2244      (-6.5%)
    cpu0-cpu3 (Cortex-A76): OPP: 2400, ThreadX: 2201, Measured: 2293      (-4.5%)

### Performance baseline

  * cpu0 (Cortex-A76): memcpy: 5833.3 MB/s, memchr: 14175.7 MB/s, memset: 8793.9 MB/s
  * cpu0 (Cortex-A76): memcpy: 5595.0 MB/s, memchr: 13557.7 MB/s, memset: 8398.5 MB/s
  * cpu0 (Cortex-A76): memcpy: 5610.2 MB/s, memchr: 12562.5 MB/s, memset: 8393.7 MB/s
  * cpu0 (Cortex-A76): memcpy: 5604.5 MB/s, memchr: 12071.8 MB/s, memset: 8158.3 MB/s
  * cpu0 (Cortex-A76): memcpy: 5583.0 MB/s, memchr: 11777.0 MB/s, memset: 7997.3 MB/s
  * cpu0 (Cortex-A76): memcpy: 5599.3 MB/s, memchr: 11396.6 MB/s, memset: 8037.3 MB/s
  * cpu0 (Cortex-A76): memcpy: 5584.6 MB/s, memchr: 11045.0 MB/s, memset: 8253.4 MB/s
  * cpu0 (Cortex-A76): memcpy: 5609.0 MB/s, memchr: 11240.9 MB/s, memset: 7811.1 MB/s
  * cpu0 (Cortex-A76) 16M latency: 109.7 109.2 110.7 107.3 107.4 113.2 148.7 197.1 
  * cpu0 (Cortex-A76) 16M latency: 109.9 109.8 105.9 105.7 107.7 116.7 147.1 201.0 
  * cpu0 (Cortex-A76) 16M latency: 107.5 110.3 105.8 106.1 109.5 112.1 148.4 195.0 
  * cpu0 (Cortex-A76) 16M latency: 109.4 106.3 109.9 109.9 107.7 111.7 146.7 201.0 
  * cpu0 (Cortex-A76) 16M latency: 112.5 110.7 105.0 106.0 106.1 114.4 148.3 201.2 
  * cpu0 (Cortex-A76) 16M latency: 109.6 106.4 104.8 110.4 110.5 112.9 147.5 202.3 
  * cpu0 (Cortex-A76) 16M latency: 108.2 106.2 109.2 107.4 107.7 111.8 149.6 201.7 
  * cpu0 (Cortex-A76) 16M latency: 110.6 108.7 108.0 106.4 110.0 113.0 146.0 197.8 
  * cpu0 (Cortex-A76) 128M latency: 123.8 121.3 123.4 122.0 124.2 121.6 122.6 131.1 
  * cpu0 (Cortex-A76) 128M latency: 122.4 121.1 123.0 121.5 121.9 120.7 123.1 128.0 
  * cpu0 (Cortex-A76) 128M latency: 122.7 122.5 121.1 121.3 123.8 122.0 122.7 131.0 
  * cpu0 (Cortex-A76) 128M latency: 122.7 122.4 121.8 122.5 122.2 120.9 123.6 130.3 
  * cpu0 (Cortex-A76) 128M latency: 122.1 121.3 123.2 127.0 122.8 122.5 123.6 131.9 
  * cpu0 (Cortex-A76) 128M latency: 122.4 123.4 122.4 121.5 121.7 121.6 124.6 130.1 
  * cpu0 (Cortex-A76) 128M latency: 123.1 122.9 122.4 123.1 121.9 119.8 122.3 130.0 
  * cpu0 (Cortex-A76) 128M latency: 121.5 121.2 123.1 120.4 122.1 123.3 122.8 128.8 
  * 7-zip MIPS (3 consecutive runs): 7940, 7884, 7853 (7890 avg), single-threaded: 2890
  * `aes-256-cbc     508247.02k   888119.32k  1132989.35k  1170084.86k  1194030.42k  1219067.90k (Cortex-A76)`
  * `aes-256-cbc     459408.67k   897897.73k  1055599.70k  1196050.09k  1157909.16k  1221984.26k (Cortex-A76)`
  * `aes-256-cbc     477768.62k   866586.60k  1086353.24k  1144383.83k  1173211.82k  1178501.12k (Cortex-A76)`
  * `aes-256-cbc     483928.96k   845066.09k  1095326.21k  1150651.39k  1183817.73k  1210231.47k (Cortex-A76)`
  * `aes-256-cbc     468158.78k   879290.67k  1055410.09k  1155632.47k  1136997.72k  1174765.57k (Cortex-A76)`
  * `aes-256-cbc     471090.47k   876449.43k  1036192.94k  1134801.92k  1192716.97k  1193033.73k (Cortex-A76)`
  * `aes-256-cbc     452475.42k   879628.48k  1102630.91k  1082959.87k  1168313.00k  1188173.14k (Cortex-A76)`
  * `aes-256-cbc     467721.51k   840143.21k  1064928.85k  1125768.87k  1186747.73k  1158518.10k (Cortex-A76)`

### PCIe and storage devices:

  * Raspberry RP1 PCIe 2.0 South Bridge: Speed 5GT/s, Width x4, driver in use: rp1, 
  * 117.8GB "Longsys USD00" UHS SDR104 SDXC card as /dev/mmcblk0: date 10/2024, manfid/oemid: 0x0000ad/0x4c53, hw/fw rev: 0x1/0x0

### Swap configuration:

  * /dev/zram0: 2G (0K used, zstd, 4 streams, 16K data, 69B compressed, 48K total)

### Software versions:

  * Debian GNU/Linux 13 (trixie)
  * Compiler: /usr/bin/gcc (Debian 14.2.0-19) 14.2.0 / aarch64-linux-gnu
  * OpenSSL 3.5.4, built on 30 Sep 2025 (Library: OpenSSL 3.5.4 30 Sep 2025)    
  * ThreadX: 69471177 / 2025/05/08 15:13:17 

### Kernel info:

  * `/proc/cmdline: reboot=w coherent_pool=1M 8250.nr_uarts=1 pci=pcie_bus_safe cgroup_disable=memory numa_policy=interleave nvme.max_host_mem_size_mb=0  numa=fake=8 system_heap.max_order=0 smsc95xx.macaddr=2C:CF:67:35:66:D3 vc_mem.mem_base=0x3fc00000 vc_mem.mem_size=0x40000000  console=ttyAMA10,115200 console=tty1 root=PARTUUID=94966f0a-02 rootfstype=ext4 fsck.repair=yes rootwait quiet splash plymouth.ignore-serial-consoles cfg80211.ieee80211_regdom=GB`
  * Vulnerability Spec store bypass:         Mitigation; Speculative Store Bypass disabled via prctl
  * Vulnerability Spectre v1:                Mitigation; __user pointer sanitization
  * Vulnerability Spectre v2:                Mitigation; CSV2, BHB
  * Kernel 6.12.47+rpt-rpi-2712 / CONFIG_HZ=250

All known settings adjusted for performance. Device now ready for benchmarking.
Once finished stop with [ctrl]-[c] to get info about throttling, frequency cap
and too high background activity all potentially invalidating benchmark scores.
All changes with storage and PCIe devices as well as suspicious dmesg contents
will be reported too.

</details>

<img width="800" height="600" alt="memory_bandwidth" src="https://gist.github.com/user-attachments/assets/03549c8c-a5a3-4235-965c-c911a34ce8c1" />

## Phoronix Test Suite

See: [geerlingguy/sbc-general-benchmark.sh](https://gist.github.com/geerlingguy/570e13f4f81a40a5395688667b1f79af):

  - pts/encode-mp3: 11.574 sec
  - pts/x264 1080p: 18.40 fps
  - pts/x264 4K: 3.96 fps
  - pts/phpbench: 426171
  - pts/build-linux-kernel (defconfig): 2458.687 sec