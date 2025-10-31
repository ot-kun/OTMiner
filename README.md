# OTMiner
ESP32 miner with sha256 Hardware Acceleration

## Introduction
This project should be fun if it is expandable. Again, you should know it is really really low possibility to actual mine a Block. Higher hashrate actually meaningless, but fun for me to challenge. And I will do other ESP32 benchmark and testing, just take time. Especially ESP32 C3 extramely low power consumption compare to ESP32 S3(0.45W) or ESP32 D0WD(0.6W). Near 1 S3 or 1 D0WD power consumption can run 3~4 C3. So the project will be seperated into few part.
1. ESP32 C3 miner(standalone)
2. ESP32 C3 stack Miner(5x ESP32 C3 to provide over 1MH/s, only 4 board doing mining, 1 WIFI, target Solar Power, 🛠️sourcing the solar panel at the moment)
3. ESP32 C3 cube Miner (32 to 96"or even more" C3 in Cube form)

## Caution
ESP32 is a powerful device, however it is no way or extremely low possibility to actual mine a BTC Block in terms of lightyear. "To infinity and beyond!"

## Benchmark
- **Latest** 0.11W
- ESP32 C3 Low Power Mode - 0.16W
- <img width="424" height="222" alt="ESP32_C3_Benchmark_SHA256_LP_0 16W" src="https://github.com/user-attachments/assets/015d1b74-52f9-47f0-a5d2-c63fb527512d" />
- ESP32 C3 High Power Mode - 0.18W
- <img width="431" height="221" alt="ESP32_C3_Benchmark_SHA256_HP_0 18W" src="https://github.com/user-attachments/assets/cd663d64-37b1-4df8-85a8-46cb10ef4ec2" />


Version1.1 : ESP32 C3 HP Mode ~~0.15W@425khs+~~ High Power Mode not working well, but possible to fix it, need time. v1.1-rc on site is a demo, the release one not yet upload. Few more things to fix in order to boost the whole thing back to over 400khs+. Not much time on fixing the project, i knows. Only works few days is not good enough, i know. But Low Power mode at less 355khs+, good enough and not perfect enough.

- ESP32 D0WD Performance @ 0.45W
- <img width="551" height="211" alt="ESP32_D0WD" src="https://github.com/user-attachments/assets/0ea0ec6b-e717-4151-9eb6-87f82daea9a8" />
- **Latest** 366khs+, but still too high power consumption
- Applied my version of SHA loop logic, not much performance increase, around 360kh/s, just few kh/s more
- If someone need this version/CYD version, please ask. Just a few k hashrate more.

- ESP32 S3 @ 0.45W
- **Latest** 383khs+ but still too high power consumption
- 328kh/s+, higher than NerdMiner, however not meet what I want. Maybe due to my logic work better on RISCV, I should try ESP32 P4/C6

- ESP32 C6
- I am still waiting one for testing

**How it works❓**

It has 2 power modes to switch, so in avg. it sits around 400-410khs. Since stability issue, the tune down one with WIFI @ 355kh/s+

## Versions ##

**V1.2 Under Testing**
- ESP32 C3 @ 402khs+ just LP Mode.

**V1.1 Release**
- 0.11w~0.12w avg. 355khs+ (LP Mode only)
- Fixed most of the issues, running great. Few more enhancement, but no much visible performance like few more hashes/second

**V1.1 Pre-release**
- +6khs enhancement

**RC V1.1 - DEMO**
- ESP32 C3 @ 355khs+ (0.13W) LP@ 345khs+(0.11W)
- overflow issue fixed.
- Stability enhanced
- little weight powerful miner
- public-pool issue fixed 

**ESP32 D0WD 360khs+ (0.45W), CYD works as well, but nothing huge improvements with just few more khs.**
- ❌no release since no big different to Nerdminer, just few khs more.

**Release V1.0(deleted‼️)**
- ESP32 C3 @ 400-410khs (@0.15W)
- Further enhance the SHA loop, no stacking for verify, directly verify and send back to pool.
- ❌deleted due to overflow after few days(stressful sha loop)
- No other ESP32 device versions right now, low in funding, just a self fun project

## Introduction
**OTMiner**
- no fancy UI, just a hash unit. Keep it simple and easy scale up. 
- Once setup and forget about it.

**OTMiner Stack**
- I would like to add a mini web server, so users can config or even view each miner performance.(I am bad at making UI)
- A stack is a simple solution to reduce WIFI noise and just shows an 1 device, further reduce power consumption
- No additional chips or PCB, just stack and go

**OTMiner Cube**
- Multiple ESP32 C6 as slave mining, using ESP32 C3(no mining) to control(maybe).
- 32 ESP32 C3/C6 supermini as mining slave units, which light up its LED while submit a valid share, so it's like a LED Cube.
- 96 or even more ESP32 C3/C6 mining slave units should be great.
  

## Configurations
~~Configurations through Serial the first time.~~
- Added WIFI AP for Setup (Although some KH/s lower during adding this....T_T)
- WIFI AP SSID: OTMinerAP
- WIFI AP PWD: OverTimeMiner
- `WIFI SSID`
- `WIFI PASSWORD`
- `POOL URL` (without stratrum+tcp)
- `POOL PORT`
- `ADDRESS`

## Todos
Expected valid share with turn on the led on mining slave board
- ✅Further tunning should be in V1.1 (not yet, aims for slighty reduce power usage, slighty more hashes/s, more stable)
- 🛠️Stacking option(show as 1 unit, just 1 wifi, reduce rf noise)
- ❌ETHernet instead of WiFi (keep power consumption at mininal, keep more cpu on handling)
- Web server config page, so users can view and config the miner
- Changing the power input from 5v to 12v(able to scale up like more than 200 mining slaves)
- 32 ESP C3/C6 mining units on a single PCB (easy to stack more mining slaves)
- 96 ESP C3/C6 mining units on a single PCB (easy to stack more mining slaves)

## Modification
- Mainly rewrite the whole SHA calculation and Fully utilized the hardware acceleration. Just setup, plug-in and see the result.
~~- Not working well with public-pool(not sure why), if you using your own ckpool build from github should be fine.~~
- Wifi Setup and stratrum handling mainly using NerdMiner v2

## Install from website
~~A demo binary with limited use may release for around 60 minutes~~
- unlimited ESP32Miner version just for C3
- Use [https://espressif.github.io/esptool-js/](https://espressif.github.io/esptool-js/) and install binaries on your board.

## Original Source of the project
- Original project https://github.com/valerio-vaccaro/HAN
- Part of the source code from https://github.com/BitMaker-hub/NerdMiner_v2/

## Supports & Donations
- Really need some funding to continue
- Bitcoin : 1AnNcAMkYaagAW8A3V2gjgbbnpEWuqv7JH
