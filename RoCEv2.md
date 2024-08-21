# RoCEv2
Originating from Infiniband, RoCE traditionally required Lossless Fabric. Mellanox ConnectX4 interface card and its successors, enables RoCE to run on Lossy Fabric as well.
- Lossy Fabric - A Fabric which doesn't enforce priority flow control (PFC).
- Connect-X NICs implement hardware based congestion control mechanisms - 1000x faster than software-based

Any type of Ethernet Network
- Lossless
  - ECN
  - QOS
  - PFC
- Lossy
  - ECN
  - QOS

DCQCN - Data Center Quantized Congestion Notification (Lossy Network)
- RoCE congestion control algorithm designed by Mellanox and Microsoft
- When ECN switches and routers queues begin to fill up, they mark packets with an ECN mark. Then the receiver server marks the packets with a CNP packets. The DCQCN operates on the NICs.

![image](https://github.com/user-attachments/assets/fac1249c-a0e1-4cbf-9c18-bef6973fb2df)

Done over
- Layer 2 under PCP Tag
- Layer 3 under DSCP Tag

![image](https://github.com/user-attachments/assets/5b98e6ca-ed9b-4097-a166-44629cdf34d3)

Link Layer Discovery Protocol (LLDP) - let the switch automatically configure the adapter according to the settings

Accelerate Lossly Performance
- Adaptative Retransmission
- Transmission Window
- Slow start
  - Enabled using MLXREG Tool
  - LSPCI Command to get to the Mellanox device name for connectors

RoCEv2 versus InfiniBand

![image](https://github.com/user-attachments/assets/7065480f-b2e6-4094-87ad-609e41f035da)

ECMP Routing (Equal-cost Multipath) - network routing strategy that allows for traffic of the same session or flow - that is, traffic with the same source and destination - to be transmitted across multiple paths of equal cost.

https://community.fs.com/article/an-indepth-guide-to-roce-v2-network.html

![image](https://github.com/user-attachments/assets/448198cf-7bc5-4477-971f-a39e863cc55a)

