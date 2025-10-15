# OTMiner
ESP32 miner with sha256 Hardware Acceleration

## Introduction
I do have a NMMiner which showing 1MHs, while my pool speaks otherwise like around 750khs running for 1~2 week. That is what I wondering the whole SHA loop verification simply stacking. Then I do think ESP32 S3 should done it better. The proof of concept using ESP32 C3 because I don't have S3 in hand but C3. This project should be fun if it is expandable. Again, you should know it is really really low possibility to actual mine a Block. Higher hashrate actually meaningless, but fun for me to challenge. And I will do other ESP32 benchmark and testing, just take time.

## Caution
ESP32 is a powerful device, however it is no way or extremely low possibility to actual mine a BTC Block in terms of lightyear. "To infinity and beyond!"

## Benchmark
- ESP32 C3 Low Power Mode - 0.16W
- <img width="424" height="222" alt="ESP32_C3_Benchmark_SHA256_LP_0 16W" src="https://github.com/user-attachments/assets/015d1b74-52f9-47f0-a5d2-c63fb527512d" />
- ESP32 C3 High Power Mode - 0.18W
- <img width="431" height="221" alt="ESP32_C3_Benchmark_SHA256_HP_0 18W" src="https://github.com/user-attachments/assets/cd663d64-37b1-4df8-85a8-46cb10ef4ec2" />
High Power Mode +6 performance with 12.5% power consumption

**How it works❓**

It has 2 power mode to switch, so in avg. it sits around 400-410khs.

## Release V1.0
- ESP32 C3 @ 400-410khs (@0.15W), further enhance the SHA loop, no stacking for verify, directly verify and send back to pool.
-
- No other ESP32 device versions right now, low in funding, just a self fun project


## Introduction
- no fancy UI, just a hash unit. Keep it simple and easy scale up. Or just a OLED Display is more than enough. I would like to know if some mining units keep sending nice share or no share at all. I need all the data, so a scaling up is needed.
- Multiple ESP32 C6 as slave mining, using ESP32 S3 to control(maybe).
- 32 ESP32 C3/C6 supermini as mining slave units, which light up its LED while submit a valid share, so it's like a LED Cube. 

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
- Further tunning should be in V1.1 (not yet, aims for slighty reduce power usage, slighty more hashes/s, more stable)
- ETHernet instead of WiFi (keep power consumption at mininal, keep more cpu on handling)
- Changing the power input from 5v to 12v(able to scale up like more than 200 mining slaves)
- 32 ESP C3/C6 mining units on a single PCB (easy to stack more mining slaves)
- 96 ESP C3/C6 mining units on a single PCB (easy to stack more mining slaves)

## Modification
- Mainly rewrite the whole SHA calculation and Fully utilized the hardware acceleration. Just setup, plug-in and see the result.
- Not working well with public-pool(not sure why), if you using your own ckpool build from github should be fine.
- Wifi Setup and stratrum handling mainly using NerdMiner v2

## Install from website
~~A demo binary with limited use may release for around 60 minutes~~
- unlimited ESP32Miner version just for C3 for testing
- Use [https://espressif.github.io/esptool-js/](https://espressif.github.io/esptool-js/) and install binaries on your board.

## Original Source of the project
- Original project https://github.com/valerio-vaccaro/HAN
- Part of the source code from https://github.com/BitMaker-hub/NerdMiner_v2/

## Supports & Donations
- Really need some funding to continue
- Bitcoin : 1AnNcAMkYaagAW8A3V2gjgbbnpEWuqv7JH
