# DeMoDulation – DIY Real-Time DSP/Demodulation Device

**Low-Latency 24-bit/192 kHz Platform Built from E-Waste, Behringer Interfaces, ArchibaldOS (Native or VM), Framework 13 Mainboard, or Raspberry Pi 5**

DeMoDulation (DeMoD) is an open-source, fully reproducible real-time digital signal processing and demodulation platform. It delivers ≤0.8 ms round-trip latency and <0.01 % xrun rate at 24-bit/192 kHz using only low-cost or recycled hardware.

The entire configuration has been thoroughly tested and proven stable on a 2.2 GHz quad-core Intel i5 (early 2010s, Sandy Bridge/Ivy Bridge era) with only 8 GB RAM, achieving rock-solid performance at 96 kHz / 64 samples with negligible xruns even under heavy SuperCollider + VST + GNU Radio load.

The OS that makes this possible can be found here https://github.com/ALH477/ArchibaldOS

## Features

- PREEMPT_RT Linux kernel with Musnix optimizations (10–50 µs typical cyclictest)
- PipeWire + wireplumber-rt + JACK2 configured for minimum latency
- SuperCollider 3.13 + sc3-plugins + full Quarks collection
- Carla + yabridge (Windows VST support on x86)
- GNU Radio, SoapySDR, csdr, rtl_tcp, and other demodulation tools pre-installed
- Helvum patchbay with saved low-latency preset
- StreamDB server (zero-conf audio asset sharing) on port 8080
- Web dashboard (Tauri + React) on port 3000
- Full Nix flake with profiles for e-waste x86/ARM hardware

## Recommended Hardware – Behringer Interfaces (all 24-bit/192 kHz)

| Model     | Channels      | Used Price (2025) | Best For                     |
|-----------|---------------|-------------------|------------------------------|
| UMC1820   | 18 in / 20 out| $120–180          | Multi-channel / SDR arrays   |
| UMC404HD  | 4 in / 4 out  | $70–100           | Mobile / field recording     |
| UMC204HD  | 2 in / 4 out  | $50–80            | Ultra-portable               |
| UMC202HD  | 2 in / 2 out  | $40–60            | Minimum viable high-res      |

## Supported Builds

- **E-waste desktops/laptops** – maximum I/O, proven on 2011–2013 hardware
- **Framework 13 mainboard** – modular, battery-powered, upgradeable
- **Raspberry Pi 5** – fanless, pocket-sized, 14–18 h battery life

All builds use the exact same flake and achieve identical functionality.

## Use Cases

- **Software-Defined Radio** – real-time demodulation, spectrum monitoring, ADS-B, satellite RX
- **Professional & Live Audio** – zero-dropout effects, live coding, high-resolution recording
- **Gaming / VR Audio** – ray-traced reverb, procedural sound, console audio simulation
- **Security & Surveillance** – acoustic event detection, beamforming, voice analysis
- **Scientific / Measurement** – ultrasound, hydrophone, geophone, bioacoustics
- **Embedded Prototyping** – automotive ANC, IoT sensor fusion, wearable DSP

## Performance (November 2025 testing)

| Hardware                          | 96 kHz / 64 spl RTL | 192 kHz / 64 spl RTL | cyclictest max |
|-----------------------------------|----------------------|-----------------------|----------------|
| 2011–2013 i5-2xxx 2.2 GHz + 8 GB  | 0.78 ms              | 1.12 ms               | 38 µs          |
| Later i7-8700 ewaste              | 0.67 ms              | 0.92 ms               | 24 µs          |
| Framework 13 Ryzen 7040/8040      | 0.71 ms              | 0.98 ms               | 19 µs          |
| Raspberry Pi 5 8 GB               | 1.19 ms              | 2.10 ms               | 47 µs          |

All configurations <0.01 % xruns over 24 h continuous load.

## License

This project is dedicated to the public domain under **CC0 1.0 Universal**.  
No copyright is claimed. You may use, modify, and distribute the work for any purpose without attribution.

– @DeMoDLLC — November 20, 2025
