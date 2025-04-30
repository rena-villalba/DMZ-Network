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

