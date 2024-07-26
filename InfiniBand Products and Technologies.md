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

Physical Layer defines the specifications for...
- Direct Attach Copper (DAC)
- Active Optical Cables (AOC)

## Host Channel Adapters (For InfiniBand)
Key Features
- Up to 400 Gb/s over low latency
- Multiple Form-factor Support
- Scalable Design

![image](https://github.com/user-attachments/assets/54722ef2-dab9-49c1-863f-a06ff1230d72)

![image](https://github.com/user-attachments/assets/3c64a8ca-802e-4a30-847f-e9ee89dbd89a)

Port Splitting 
- Can operate at 100 Gbps after they have had their data lanes split

![image](https://github.com/user-attachments/assets/522e9a04-f1a9-463d-ac5e-317ad7a6aca2)

![image](https://github.com/user-attachments/assets/d56cafb2-bef2-4107-8987-43fbec75ac2d)

- Multihost support allowing 4 different CPUs over 4 PCIe lanes to be served on a single HCA
- Socket Direct Cards enables RDMA for all GPU CPU pairs

![image](https://github.com/user-attachments/assets/5f5b5c7c-3d25-4a81-bfe5-14eaf00024d3)

## Introduction to InfiniBand Switch Systems
- EDR - Enhanced Data Rate (100 Gbps)
- HDR - High Data Rate (200 Gbps)
- NDR - Next Data Rate (400 Gbps)
  - These are edge switches that can be managed interally or externally
 
![image](https://github.com/user-attachments/assets/cd652cd8-6b13-4553-816b-7b7560845403)

NVIDIA Edge Switches
- EDR Switches:
  - SB7700, SB7780, SB7790, SB7890
  - EDR Lanes Picture Below
- HDR Switches:
  - QM8700, QM8790 (40 port switches) 
- NDR Switches:
  - QM9700, QM9790 (32 physical OSFP connectors each one with 2 NDR ports of 400 Gbps)
- Port Splitting:
  - NDR and HDR can be further split for more ports
    - HDR-100 (200 originally) - 2x 50Gbps lanes running in parallel
    - NDR-200 (400 originally) - 2x 100 Gbps lanes running in parallel
- SHARP (Scalable Hierarchical Aggregation and Reduction Protocol):
  - offloads data from the CPU to the switch fabric itself; reduces congestion & multiple CPU interventions
- Switch Management Features:
  - Only Internal Switches support management via SNMP, IP, IPv6, CLI, or web gui
    - 2x RJ-45 port
    - USB port
    - RS232 on DB9

![image](https://github.com/user-attachments/assets/442eb0e5-c2db-4ac5-8b28-744dbfddd76f)

## UFM (Unified Fabric Manager) Overview 
UFM combines
- Real-time network telemetry collection
- High-end monitoring and orchestration tools
- AI analytics

### UFM Telemetry 
- CLI-Based
- Collector Streaming: Can stream and export telemetry via FluentBit and Prometheus exporter to third party collectors

### UFM Enterprise
- Management
- Orchestration
- Monitoring

UFM Enterprise can be a software installation for linux distributions, docker container, or UFM Appliance. Also has the UFM Telemetry and exposes it to the REST API and Web UI.
![image](https://github.com/user-attachments/assets/754987e0-ec95-4a82-b8e6-00ef057fdfee)

### UFM Cyber-AI
Dedicated platform combining UFM Telemetry and Enterprise.
- Telemetry for the data
- Enterprise for topology awareness
Runs predictive models that generate smart user notifications on link failure, network anomalies, and tenant irregularities. 
