## Experiment 02 – Cellular Hotspot (Phone, Tablet, Laptop)

### Tooling
Packet sniffing application **Wireshark** on a laptop. My personal mobile phone Telekom SIM card.

### Motivation
Conduct preliminary testing to support design thinking and hardware selection. Identify potential showstoppers early in the process.
### Setup
- Tablet or Phone with 5G/LTE SIM as cellular network access point.
- Laptop, Tablet, Phone either configured as Wi-Fi hotspot. The device with cellular connectivity is tethered to it, hotspot configured to offer transparent link.
- Appliance connected directly to hotspot.
- Tablet or Phone connected by USB-tethered to Laptop for packet sniffing.
- Temporary placement near appliance.

### Result
✅ Successful

### Observations
- App showed real-time status
- End-of-cycle notifications worked
- Firmware update possible
- Cellular signal strength low but usable.
- EcoFeedback report observed 

### Lesson Learned
- Cellular connectivity is viable. (Worked as standalone solution hotspot/cellular connection on tablet)
- Placement near a cellar window instead on top of washing machine/dryer stack advisable for better cellular connection.
- Appliance initial configuration with hotspot not feasible if the device (phone) is tethered and/or hotspot running the Miele app!
- Tethered connections where difficult to capture the desired appliance traffic.
- Only during sniffing sessions the connection **(or in particular this setup)** seems to be very brittle
- Later regular usage with the tablet hotspot/cellar network solution revealed that to a certain extend reconnection attempts occur. 
Otherwise the mobile app wouldn't switch back and forth between not connected appliance and active wash
cycle. Since I am using the tablet setup solution for quite some month, I can confirm it works reliably with a Vodafone Data SIM now and placed at the window frame.

### Analysis

01_sniffing_session
- Tablet has my SIM card inserted and is simultanously cellular link/hotspot. The laptop is sniffing within the same network. Everything was placed on top.
- We see a lot of ARP protocol and MDNS protocol packets, everything else is related to my laptop.
- We did a complete WoolWashCycle and the Miele app reported to me the finish indication. And the EcoFeedback stats!
- Remainder, we had direct internet access without any tether for the appliance and we did not attempt to capture the appliance traffic.

02_sniffing_session
- This time established hotspot by laptop and used the phone as tether for internet connectivity.
- On/Off did great, we see the TLS protocol and those packets indicate a session.
- Then something broke down, i don't know. I couldn't find any of those packets. Something was lost and so the connection 
didn't work and no report of the finish indication trough the Miele app.

