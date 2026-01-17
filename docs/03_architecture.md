# Architecture

## Explored Architectures

Several architectures were evaluated:

- Wi-Fi repeater from home network
- Laptop-based LTE hotspot (USB tethering)
- Raspberry Pi with LTE modem or HAT
- Dedicated LTE router with external battery
- Android tablet acting as LTE hotspot

## Observations

- Laptop-based solutions were unstable due to OS behavior and background traffic
- Raspberry Pi solutions introduced significant power and complexity overhead
- Dedicated LTE routers improved isolation but added cost and battery challenges
- The tablet-based solution proved reliable, power-efficient, and simple

## Reference Architecture

The current reference architecture uses:
- An Android tablet with LTE connectivity
- Wi-Fi hotspot enabled permanently or on schedule
- Internal battery as primary power source
- No per-cycle user interaction required

The architecture favors robustness and usability over modularity.
