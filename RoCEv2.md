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

![image](https://github.com/user-attachments/assets/7065480f-b2e6-4094-87ad-609e41f035da)

https://community.fs.com/article/an-indepth-guide-to-roce-v2-network.html

![image](https://github.com/user-attachments/assets/448198cf-7bc5-4477-971f-a39e863cc55a)

