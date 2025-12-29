## Experiment 01 – Wi-Fi Repeater

### Tooling
Wi-Fi network scanning application **inSSIDer by Metageek** on a laptop. Screenshots were taken as quick measurement snapshots.
Additional Wi-Fi scanning was done via mobile phone system settings. 
Main Router: Compal CH7465LG-LC
Secondary Router: Asus RT-N66U

### Motivation
Extending the Wi-Fi reach to the appliance. Any reliable link would be sufficient, no high troughput needed.

### Setup
- High-power secondary router in repeater mode ( tested with both wired and wireless parent ap connection)
- Multiple fixed channels tested on both routers (2.4 GHz / 5 GHz)
- Channel width tuning manually instead of automatic setting
- Various Wi-Fi configuration tweaks to achieve the most stable link
- Physical repositioning (relocation)
- Orientation adjustments

### Result
❌ Failed

### Findings
- Severe attenuation
- Unreliable discovery
- Inconsistent RSSI
- No stable link at appliance location

### Lesson Learned
Wi-Fi is not a viable transport method to the cellar. At best we have reach the doorways of the room.
Measured output power at less than 1 meter distance of main router:
- 2.4 GHz, channel 13: –25 dBm
- 5 GHz, channel 44: –15 dBm
Direct penetration to cellar was not enough with these output powers. Anyhow placing the secondary router as extension did not yield
the desired effect because somehow the stairs and full metal railing and corners likely shadow it or the interference is in addition to much.

### Note
- Data is not committed due to privacy protection.
- Two Wi-Fi networks reach my appliance, one is from a neighbour who doesn't want to share and the other origin is unknown.
