---
title: Hardware V2.0
---

# Hardware Improvements for Version 2.0

The Version 2.0 redesign focuses on improving signal integrity, power efficiency, and debugging capability by addressing several limitations found in the current subsystem. The first major improvement involves optimizing the analog signal conditioning stage. In the original design, the MCP6004 Op-Amp, combined with capacitors C4 and C6, unintentionally created an active low-pass filter that suppressed the high-frequency square wave needed for accurate soil moisture readings. To correct this, the new design removes both capacitors to increase bandwidth and reconfigures the Op-Amp as a Schmitt Trigger, adding hysteresis and producing a clean digital square wave for the microcontroller. Additionally, unused channels of the MCP6004 will now be used to drive an active shield trace, which helps reduce parasitic capacitance from the soil.

The second improvement focuses on power efficiency and operational feedback. The linear LM7805 regulator is being replaced with a pin-compatible switching regulator to eliminate unnecessary heat dissipation and extend battery life. Instead of using the fixed red power LED, the system will now rely on the blue debug LED connected to RB6 as a software-controlled heartbeat indicator. Blinking at 1 Hz, this LED provides immediate confirmation that the PIC18F57Q43 is powered and successfully executing code.

The final set of improvements enhances testability and safety. Dedicated through-hole ground loops will be added near the Op-Amp and GPIO headers to make oscilloscope probing easier and less noisy. Existing flat test pads such as TP_5V and TP_AOUT0 will be upgraded to standard 0.1-inch headers for more reliable jumper connections. Finally, a series resistor or PTC fuse will be added to the Ribbon Cable Connector’s power line to protect the main board from accidental short circuits. These changes together make the subsystem more robust, efficient, and easier to troubleshoot.
