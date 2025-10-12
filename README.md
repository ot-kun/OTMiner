# OTMiner
ESP32 miner with sha256 Hardware Acceleration

## Caution
ESP32 is a powerful device, however it is no way or extremely low possibility to actual mine a BTC Block in terms of lightyear. "To infinity and beyond!"

## Benchmark
- ESP32 C3 Low Power Mode - 0.16W
- <img width="424" height="222" alt="ESP32_C3_Benchmark_SHA256_LP_0 16W" src="https://github.com/user-attachments/assets/015d1b74-52f9-47f0-a5d2-c63fb527512d" />
- ESP32 C3 High Power Mode - 0.18W
- <img width="431" height="221" alt="ESP32_C3_Benchmark_SHA256_HP_0 18W" src="https://github.com/user-attachments/assets/cd663d64-37b1-4df8-85a8-46cb10ef4ec2" />
High Power Mode +6 performance with 12.5% power consumption

## Introduction
- no fancy UI, just a hash unit. Keep it simple and easy scale up. Or just a OLED Display is more than enough. I would like to know if some mining units keep sending nice share or no share at all. I need all the data, so a scaling up is needed.
- Multiple ESP32 C6 as slave mining, using ESP32 S3 to control.

## Configurations
~~Configurations through Serial the first time.~~
- Added WIFI AP for Setup (Although some KH/s lower during adding this....T_T)
- WIFI AP SSID: OTMinerAP
- WIFI AP PWD: OTMiner
- `WIFI SSID`
- `WIFI PASSWORD`
- `POOL URL` (without stratrum+tcp)
- `POOL PORT`
- `ADDRESS`

## Todos
Expected valid share with turn on the led on mining slave board
- ETHernet instead of WiFi (keep power consumption at mininal)
- 32 ESP C6 mining units on a single PCB (easy to stack more mining slaves)
- 96 ESP C6 mining units on a single PCB (easy to stack more mining slaves)


## Install from website
~~A demo binary with limited use may release for around 60 minutes~~
- unlimited version just for C3 for testing
- Use [https://espressif.github.io/esptool-js/](https://espressif.github.io/esptool-js/) and install binaries on your board.

## Supports & Donations
- Really need some funding to continue
- Bitcoin : 1AnNcAMkYaagAW8A3V2gjgbbnpEWuqv7JH


