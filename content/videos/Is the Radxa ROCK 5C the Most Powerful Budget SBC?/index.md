---
title: "Is the Radxa ROCK 5C the Most Powerful Budget SBC?"
date: 2025-07-17
draft: false
summary: "The complete benchmark results for the Radxa ROCK 5C, including tests that didn't make it into my orginal YouTube video."
tags: ["SBC", "Radxa", "Reviews"]
---
<img width="800" height="600" alt="IMG_4895" src="https://gist.github.com/user-attachments/assets/2052f002-65a6-4aff-ae2e-493b4b0cbb79" />


In this video, I review Radxa's ROCK 5C, a powerful single-board computer powered by the 8-core Rockchip RK3588S2 SoC, featuring 4x Cortex-A76 and 4x Cortex-A55 cores.

Posted on YouTube: [https://youtu.be/R3_6UD4P_OY](https://youtu.be/R3_6UD4P_OY)

---

  sbc-benchmark.md
  
  custom SBC test/report template forked from Jeff Geerling’s sbc-reviews repository
  
  created 25 January 2023
  by Jeff Geerling
  ...
  forked 10 November 2025
  by Ryder Hutchings
  modified 23 December 2025
  by Ryder Hutchings

  this template is under the MIT license

## Basic Information:

  - Board URL (official): TODO
  - Board purchased from: TODO
  - Board purchase date: TODO
  - Board specs (as tested): TODO
  - Board price (as tested): TODO

## Linux/System Information:

```
# output of `screenfetch`
TODO

# output of `uname -a`
TODO

```
## System Topology:
TODO: Paste the output of lstopo lstopo.png here (install the hwloc package to get lstopo).

Note: lstopo results may be missing some information on new and strange SoCs.

## Benchmark Results:

### CPU

#### `Geekbench 6` results: 
- See: [https://browser.geekbench.com/v6/cpu/######](TODO) and [https://browser.geekbench.com/v6/cpu/######](TODO)
- TODO Single-Core Score / TODO Multi-Core Score

#### `top500-benchmark` results:

- See: [geerlingguy/top500-benchmark](https://github.com/geerlingguy/top500-benchmark)

- TODO Gflops at TODO W, for ~TODO Gflops/W
<details>
<summary>Click to expand HPLinpack / top500-benchmark results</summary>

```
TODO
```
</details>

#### `sysbench` results:
- See: [akopytov/sysbench](https://github.com/akopytov/sysbench)

```
TODO
```
[comment]: # (sysbench cpu --cpu-max-prime=20000 --threads=4 run)

### Thermals
- See: [ryderhutchings/rk-thermal.sh](https://github.com/ryderhutchings/rk-thermal.sh)

| Test Condition           | With Heatsink (°C) | Without Heatsink (°C) | Notes |
|--------------------------|-------------------|----------------------|-------|
| Idle (Desktop)           | TODO              | TODO                | Baseline thermal behavior |
| Web Browsing             | TODO              | TODO                | Typical mixed usage range; acceptable and responsive |
| 1080p YouTube Playback   | TODO              | TODO                | Typical multimedia load; acceptable but nothing exceptional |
| 4K YouTube Playback      | TODO              | TODO                | Frequent buffering and frame drops; not recommended for 4K playback |
| stress-ng (--cpu 80)     | TODO              | TOFO                | Gradual temperature rise; remained surprisingly cool |
| sbc-bench Run            | TODO                | TODO                | Compare to stress-ng for peak temperature during full suite |

### Power
  
  - Idle shutdown power draw (at wall): TODO W
  - Idle power draw (at wall): TODO W
  - Maximum simulated power draw (`stress-ng --matrix 0`): TODO W
  - During Geekbench multicore benchmark: TODO W
  - During `top500` HPL benchmark: TODO W

### Disk

#### External microSD (USD00-128GB)

| Benchmark                  | Result |
| -------------------------- | ------ |
| iozone 4K random read      | TODO MB/s |
| iozone 4K random write     | TODO MB/s |
| iozone 1M random read      | TODO MB/s |
| iozone 1M random write     | TODO MB/s |
| iozone 1M sequential read  | TODO MB/s |
| iozone 1M sequential write | TODO MB/s |

### Network

> Note: All measurements were taken over Wi-Fi, not wired Ethernet.

`iperf3` results:

  - `iperf3 -c $SERVER_IP`: TODO Mbps
  - `iperf3 -c $SERVER_IP --reverse`: TODO Mbps
  - `iperf3 -c $SERVER_IP --bidir`: TODO Mbps up, TODO Mbps down

`nuttcp` results:

  - `nuttcp -t $SERVER_IP`: TODO / TODO sec = TODO Mbps

### GPU

`glmark2-es2` / `glmark2-es2-wayland` results:

```
TODO
```

## vkmark
N/A

## GravityMark
N/A

## AI / LLM Inference:

Basic `ollama` LLM model inference results:

Running benchmark 3 times using model: `tinyllama:1.1b`
| Run | Eval Rate (Tokens/Second) |
|-----|-----------------------------|
| 1 | TODO tokens/s |
| 2 | TODO tokens/s |
| 3 | TODO tokens/s |
|**Average Eval Rate**| TODO tokens/second |

Running benchmark 3 times using model: `deepseek-r1:1.5b`
| Run | Eval Rate (Tokens/Second) |
|-----|-----------------------------|
| 1 | TODO tokens/s |
| 2 | TODO tokens/s |
| 3 | TODO tokens/s |
|**Average Eval Rate**| TODO tokens/second |

Running benchmark 3 times using model: `llama3.2:3b`
| Run | Eval Rate (Tokens/Second) |
|-----|-----------------------------|
| 1 | TODO tokens/s |
| 2 | TODO tokens/s |
| 3 | TODO tokens/s |
|**Average Eval Rate**| TODO tokens/second |

System used around TODO W during inference.

[comment]: # (Note that Ollama will run on the CPU if no valid GPU / drivers are present. Be sure to note whether Ollama runs on the CPU, GPU, or a dedicated NPU.)

## Memory:

### `tinymembench` results:

See: [rojaster/tinymembench](https://github.com/rojaster/tinymembench)

<details>
<summary>Click to expand tinymembench benchmark results</summary>

```
TODO
```
</details>

### `c2clat` results:
See: [rigtorp/c2clat](https://github.com/rigtorp/c2clat):

Core-to-core memory latency across the CPU.

[comment]: # (If this is a new CPU/SoC, run c2clat to generate a core to core memory access latency graph: https://gist.github.com/geerlingguy/842974c0e49c201c28f4be54a05cc89c)

[Add c2clat image here]

### `sbc-bench` results:
See: [ThomasKaiser/sbc-bench](https://github.com/ThomasKaiser/sbc-bench): 

```
TODO
```

<details>
<summary>Click to expand sbc-bench benchmark results</summary>


</details>

## Phoronix Test Suite

See: [geerlingguy/sbc-general-benchmark.sh](https://gist.github.com/geerlingguy/570e13f4f81a40a5395688667b1f79af):

  - pts/encode-mp3: TODO sec
  - pts/x264 1080p: TODO fps
  - pts/x264 4K: TODO fps
  - pts/phpbench: TODO
  - pts/build-linux-kernel (defconfig): TODO sec