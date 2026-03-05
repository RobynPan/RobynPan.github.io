# DIY SmartWatch

tags: Arduino, C++, Hardware, Wearable, Open Source, Right to Repair

Commercial smartwatches are sealed, surveilled, and subscription-dependent. I wanted to build something that lived on my wrist on my own terms — a timepiece that I fully understood, could repair, and could modify without asking permission from a corporation.

The project sits at the intersection of personal technology and bodily autonomy. A watch is the most intimate computing device — worn against skin all day — and that intimacy should come with transparency.

## Hardware

The core is built around an ATmega328P (the same chip in an Arduino Uno), running at 3.3V for battery efficiency. The display is a small OLED module (SSD1306, 128×64px). A DS3231 real-time clock chip keeps accurate time even when the battery is nearly dead, thanks to its temperature-compensated crystal oscillator.

- ATmega328P @ 8MHz, 3.3V
- SSD1306 OLED 0.96" display
- DS3231 RTC with coin cell backup
- LiPo 150mAh battery + MCP73831 charger IC
- Custom PCB milled at Edinburgh Hacklab
- 3D-printed case in PLA, designed in OpenSCAD

## Software

Firmware is written in C++ using the Arduino framework. The watch runs a simple cooperative scheduler — no RTOS — cycling through display updates, button reads, and power management every 100ms. Deep sleep drops current draw to ~8µA, giving roughly 10 days of battery life.

## What I Learned

Low-power design is a discipline unto itself. Every peripheral, every line of code, affects battery life. The project taught me to think about energy the way a sculptor thinks about negative space — what you leave out matters as much as what you include.
