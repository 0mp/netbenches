Impact of enabling ipfw/pf on fastforwarding performance
  - PC Engines APU2C4 (quad core AMD GX-412T Processor 1 GHz)
  - 3 Intel i210AT Gigabit Ethernet ports
  - FreeBSD 11.0
  - 2000 flows of smallest UDP packets
  - Traffic load at 1.448Mpps (Gigabit line-rate)
  - Fastforwarding was replaced by tryforward on 11.0 and enabled by default

![Impact of enabling ipfw/pf on fastforwarding performance on FreeBSD 11.0](graph.png)

