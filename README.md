# DMZ Network Project – Cisco ASA Firewall Lab

## Project Overview

The purpose of this project is to design and implement a secure network architecture using a Cisco ASA firewall to segment internal networks from a publicly accessible DMZ environment. The goal is to simulate real-world enterprise perimeter security by controlling traffic between internal clients, a web server, and an external network using NAT, ACLs, and proper interface security levels within Cisco Packet Tracer.

## Objective 

This project simulates a typical network structure with two internal subnets and a DMZ hosting a web server. The ASA firewall is configured to enforce strict security policies that only allow necessary traffic to flow in and out of each zone. The internal PCs must access the web server securely via HTTP/HTTPS, and an external simulated device must also be able to reach the server via public IP. NAT and ACLs are implemented to tightly control access, mimicking a real-world firewall deployment scenario.

### Skills Learned

- Designing secure DMZ architectures using Cisco ASA.
- Configuring static and dynamic NAT rules on ASA.
- Writing and applying ACLs to control inter-zone communication.
- Understanding security levels and interface roles (inside, outside, DMZ).
- Testing and troubleshooting HTTP/HTTPS and ICMP traffic using Packet Tracer.
- Securing access from both internal and external sources through proper firewall policies.

### Tools Used

- Cisco Packet Tracer for full network simulation.
- Cisco ASA firewall for NAT, ACLs, and interface segmentation.
- Simulated web server, internal client machines, router, and external laptop.

## Network Topology Overview

- Internal Networks:
  192.168.25.0/24 (PC1)
  192.168.26.0/24 (PC2)

- DMZ:
  192.168.80.0/24 (Web Server at 192.168.80.10)

- Outside Network:
  203.0.113.0/24 (Simulated Internet and external laptop)

- Public NAT Mapping:
  203.0.113.100 → 192.168.80.10 (Web Server)

## Process Workflow

1. Network Design

- Create a router connecting internal networks to the ASA.
- Configure three interfaces on ASA: inside, DMZ, and outside.
- Connect a server to the DMZ and a laptop to the outside network.

2. NAT Configuration

- Apply dynamic NAT for internal-to-external communication.
- Configure static NAT to expose the DMZ web server to the outside world.

3. ACL Deployment

- Permit only HTTP/HTTPS traffic from inside to DMZ.
- Allow only return traffic from the server to internal clients.
- Explicitly permit public HTTP/HTTPS access from outside to DMZ.
- Block all unnecessary or unsolicited traffic.

4. Traffic Testing

- Use browser apps to simulate client-server access.
- Verify ICMP, HTTP/HTTPS behavior through PDUs.
- Ensure external laptop can reach the public IP of the web server.

5. Security Tightening

- Remove temporary ICMP access.
- Ensure least privilege in all ACLs.
- Validate that internal devices cannot be reached from outside.

*Img 1: DMZ Topology*<br>
![DMZ diagram drawio](https://github.com/user-attachments/assets/4bebfeb4-9360-4ebe-a8fa-66cc3a51bb7e)

*Img 2: Starting Netwrok Topology*<br>
<img width="601" alt="1 early phase" src="https://github.com/user-attachments/assets/4048f261-7b99-4536-8a88-674771a4ecd3" />

*Img 3 & 4: Accessing the Router via Console*<br>
![2 Desktop Tab](https://github.com/user-attachments/assets/11a0d382-5f9d-4586-b605-7974604cb93a)
![3 terminal application](https://github.com/user-attachments/assets/43d64225-30c8-452d-a8c9-7ffeac3fce62)

*Img 5-8: Startup configuration*<br>
![4 show ip int](https://github.com/user-attachments/assets/489258ee-7709-4359-b3b3-1d286d71b121)
![5 show running c](https://github.com/user-attachments/assets/b89f2fa8-dd77-4042-a435-d66fe67ea715)
![6 running conf](https://github.com/user-attachments/assets/52d0bc8e-7af7-4e07-b85c-47c1547cefb9)
![7 running conf](https://github.com/user-attachments/assets/cfbdb6d5-a12f-4ba5-8c7d-63a1b1598df9)

*Img 9-12: Initial Router Configuration*<br>
![8 router-basics](https://github.com/user-attachments/assets/8ff5b02d-0c56-4fea-9946-606020b448b3)
![9 router-basics](https://github.com/user-attachments/assets/c71836d6-363f-4d55-8c44-6817d6afaab5)
![10 router-basics](https://github.com/user-attachments/assets/6739469a-f588-476d-bebe-3a6f4688375e)
![11 router-basics](https://github.com/user-attachments/assets/66f51dee-e95c-4c78-844a-2f0c373c6082)

*Img 13 & 14: SSH Configuration*<br>
![12 ssh_rtconfig](https://github.com/user-attachments/assets/33407c63-55c3-4a8a-8df2-0cf9b53e56f4)
![14 linevty15](https://github.com/user-attachments/assets/7a7b8006-0e74-47ab-9cc5-fce50508c505)

*Img 15 & 16: Interfaces for both PCs*<br>
![13 interface](https://github.com/user-attachments/assets/215c8340-ae03-4889-9b71-7f0846a93c9c)
![15 interface](https://github.com/user-attachments/assets/b104818c-104d-44b9-89b9-59665da9a544)

*Img 17 & 18: Assigning static IP address to the PC (The same proces for the other one)*<br>
![16 ipconfig](https://github.com/user-attachments/assets/98046b61-b265-45ed-adf6-0863bf767e8f)
![17 ipaddress](https://github.com/user-attachments/assets/f8ed20b1-e66f-49bf-9365-dd7236f0b584)

*Img 19: Testing communication between both PCs*<br>
![18 ping_test](https://github.com/user-attachments/assets/d35f3826-743d-4855-b6a1-25c3fcb91765)

*Img 20 & 21: Router -> ASA interface and Router routing*<br>
![19 internal_net](https://github.com/user-attachments/assets/10f15b71-9308-4345-a646-460838869ae2)
![21 rt_routing](https://github.com/user-attachments/assets/4913b270-b415-47bf-84c9-934446aef091)

*Img 22 & 23: ASA interfaces and ASA routing*<br>
![20 ASA_interfaces](https://github.com/user-attachments/assets/55063793-81d1-4e16-9eb8-b4b93dfa1667)
![22 ASA_routing](https://github.com/user-attachments/assets/6d31d879-8465-4214-a80c-4239d9fc9a0e)

*Img 24: Internal Network ACLs*<br>
![22 1 internal-acls](https://github.com/user-attachments/assets/010d4633-6b6c-4f78-b0c8-dbcfae5eb1fb)

*Img 25 & 26: Server IP and Gateway*<br>
![24 server_ip](https://github.com/user-attachments/assets/68c99949-dd49-41d8-96a3-d3e2bad8e6b5)
![23 server_gateway](https://github.com/user-attachments/assets/e0b66caa-8f7b-497f-be8f-df1735a4cf99)

*Img 27: Custom ACL due to Packet Tracer Limitations*<br>
![25 final_valid_acl](https://github.com/user-attachments/assets/2b33ede4-a7be-445e-87e2-b547a1d0a2d6)

*Img 28: Internet-Router interface (The router that simulates the internet on the left of the topology)*<br>
![26 router-ASA_interf](https://github.com/user-attachments/assets/dd3795f7-04e3-40e9-a267-8139d817547c)

*Img 29: Internet-Router -> External PC interface*<br>
![28 router-external-route](https://github.com/user-attachments/assets/7bb87161-645b-48cc-9437-7fa2fd21703d)

*Img 30: Static NAT for the external traffic accessing then Web Server*<br>
![29 static-nat-accls](https://github.com/user-attachments/assets/4100d5ec-b321-4689-933b-a6a9c0cf49fd)

*Img 31: Final DMZ Topology*<br>
![30 final-topology](https://github.com/user-attachments/assets/20ad70c3-2f63-438d-8c34-8a4eabc09ae1)
