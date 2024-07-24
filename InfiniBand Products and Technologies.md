# InfiniBand Products & Technologies
## Introduction to InfiniBand
Industry standard that defines input/output architecture used to interconnect compute nodes, communication infrastructure equipment, storage, and embedded systems. The architecture is independent of Host Operating System. Can be Linux, Windows, or VMware ESXI.

InfiniBand was designed for an end-to-end solution (every layer in the OSI model)
- Maximum network utilization
- Maximum CPU utilization
- Maximum Applications Performance

InfiniBand switches - move the traffic
Subnet Manager - manages all network activities
Network Hosts - clients for which fabric is built
Host Channel Adapter - enable an InfiniBand connection between the hosts and switches
Gateway - allows for IP traffic exchanges between InfiniBand and Ethernet 
InfiniBand Router - allows for interconnectivity between multiple InfiniBand subnets

## InfiniBand Key Features
Nvidia Melanonix 

Key Features
- Simplified Management - InfiniBand is 1st architecture to truly implement vision of SDN (Software Defined Network). Subnet Manager is a program that runs and manages the entire network - allows for plug and play nodes. Has a manager and standby subnet manager
- High Bandwidth - NDR 400 Gbps... highest bandwidth, non-blocking bi-directional links
- CPU Offloads - Supports data transfer with minimum CPU intervention and is achieved by hardware-based transfer protocol, Kernel bypass, and RDMA (Remote Direct Memory Access) - Direct transfer of memory from 1 node to another without involving the CPU; GPUDirect allows direct transfer of the memory of one GPU to another GPU
- Ultra-Low Latency - Hardware offloading and accelerating mechanisms (>1000 nanoseconds)
- Network Scale-out - deploy up to 48,000 nodes on a single subnet
![image](https://github.com/user-attachments/assets/635b821d-9a14-4305-9ba3-a014c297e9f8)

- Quality of Service
- Fabric Resiliency
- Optimal Load Balancing
- SHARP MPI Super Performance
- Variety of support network topologies

## InfiniBand Architecture
![image](https://github.com/user-attachments/assets/7164145b-1cb5-4969-adc7-fa4081e5da8e)

- An application-centric approach is the key differentiator between InfiniBand and Ethernet

![image](https://github.com/user-attachments/assets/e16e17c3-2287-481e-b26c-f79f40e2b183)

### Upper Layer
![image](https://github.com/user-attachments/assets/93c91132-8028-45f8-a410-80ce00ec6eab)

### Transport Layer
![image](https://github.com/user-attachments/assets/6587d1d9-bb30-4136-aa03-5732496f3a22)

- A Host Channel Adapter (HCA) receives the signal from one of the applications, which is then sent to another HCA to transports to its application.

![image](https://github.com/user-attachments/assets/4628ac7f-db4b-4549-a21a-1f4a17ad865b)

![image](https://github.com/user-attachments/assets/01fcc65b-6096-42ff-98d0-92e4f7a56baa)

- Forwarding table calcualted by the subnet manager

![image](https://github.com/user-attachments/assets/c9e02dd8-d987-44a1-a5d4-3f9c8bc1b6ee)

- The receive buffer is meant to regulate a fast sender to a slow receiver.
- The sending node automatically tracks the receive buffer usage and transmits data only if there is space in the receiving node buffer.
  - This is a lossless network - packets are not dropped in the network during normal operation. 
