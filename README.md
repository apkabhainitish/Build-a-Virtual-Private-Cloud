# Build-a-Virtual-Private-Cloud
In this project, we designed and implemented a custom VPC to enable secure, scalable cloud architecture with controlled network access and reliable connectivity for internal and external applications.

# Overview
The Build a Virtual Private Cloud (VPC) project is designed to establish a secure, customized network within AWS by creating a Virtual Private Cloud that supports controlled access and internet connectivity. This project involves setting up a VPC, creating a public subnet, and configuring an Internet Gateway to allow external access to resources within the VPC.

# Data Architecture Diagram

# Project Goals

# Creating an Amazon VPC
Designed and created a new Amazon VPC to establish an isolated network environment, specifying an IP address range using a CIDR block (Classless Inter-Domain Routing).
The VPC allows complete control over network configurations and facilitates resource organization within a dedicated private network on AWS.

# Creating a Public Subnet
Configured a public subnet within the VPC, assigning a portion of the VPC’s IP address range to this subnet.
The public subnet is placed in an Availability Zone (AZ) for high availability, and resources within this subnet can be directly accessed by users through the internet.

# Configuring an Internet Gateway
Created and attached an Internet Gateway to the VPC, enabling internet access for resources within the public subnet.
Configured the route table associated with the public subnet to direct all outbound traffic to the Internet Gateway, ensuring that instances in the public subnet can connect to and be accessed from the internet.

# Project Outcome
Through this project, we successfully established a foundational VPC network in AWS that supports internet connectivity for public-facing resources. By creating an Amazon VPC with a public subnet and attaching an Internet Gateway, we have enabled secure, managed access to resources from the internet, essential for web servers, public applications, and services that require user accessibility. This VPC configuration forms a reliable base for further expanding network architectures, enabling the deployment of secure and scalable applications on AWS.

# AWS Services 

# Amazon VPC 

Amazon VPC (Virtual Private Cloud) is a customizable, isolated network within the AWS cloud where users can deploy and manage their resources, such as EC2 instances, RDS databases, and other AWS services. With a VPC, users have complete control over their network environment, including IP address ranges, subnets, routing tables, and security settings. By using a VPC, organizations can create secure cloud environments that mimic traditional data centers but with the flexibility and scalability of the cloud.

Network Isolation and Security: Amazon VPC provides network isolation by creating a logically separate network space within AWS. It allows users to define security settings, such as security groups and Network Access Control Lists (NACLs), to control inbound and outbound traffic.

Flexible Network Configuration: VPCs allow users to customize their IP addressing schemes, set up multiple subnets, and configure route tables to control the traffic flow within the VPC and to external networks.

Scalability: VPCs are highly scalable and can accommodate various workloads by supporting multiple subnets across different Availability Zones for redundancy and high availability.

# Internet Gateway

An Internet Gateway is a VPC component that provides a connection between a VPC and the internet, enabling resources within the VPC to send and receive data over the internet. It allows instances within public subnets to have direct access to the internet.

Connecting to Public Subnets: An Internet Gateway is attached to a VPC and is typically used in combination with a public subnet. Any instance in a public subnet with a route to the Internet Gateway can access the internet.

Routing Traffic: Internet Gateways work by enabling outbound traffic to the internet and inbound traffic from the internet for instances in public subnets. The route table associated with the subnet must have a route directing 0.0.0.0/0 traffic to the Internet Gateway.

Secure Connectivity: Internet Gateways do not interfere with VPC security settings, meaning you can still control access to internet-facing resources using security groups and NACLs. This ensures that only authorized traffic can reach resources in the VPC.

Internet Gateways are essential for applications that require public access, such as web servers or APIs, providing a secure link between AWS resources and the internet.

# Key Concepts

# IPv4

IPv4 (Internet Protocol version 4) is the most commonly used internet protocol, defining IP addresses as 32-bit numbers. An IPv4 address is written as a series of four decimal numbers separated by dots, such as 192.168.1.1.

Private IPv4 Addresses: Within an AWS VPC, resources can be assigned private IPv4 addresses. These addresses are accessible only within the VPC or connected networks and are not routable over the internet.

Public IPv4 Addresses: Public IP addresses allow resources to communicate over the internet. For example, an EC2 instance in a public subnet can be assigned a public IPv4 address, enabling direct internet access.

Elastic IP Addresses: An Elastic IP is a static public IPv4 address that can be attached to an instance to ensure it has a consistent public address, even if it’s restarted or moved to another instance.
IPv4 is crucial in a VPC setup for ensuring resources have unique and identifiable addresses, either within the VPC or externally via the internet.

# CIDR 

CIDR (Classless Inter-Domain Routing) notation is a method used to define IP address ranges within a VPC. In CIDR notation, an IP address is followed by a slash and a number (e.g., 10.0.0.0/16). The number after the slash represents the number of bits in the prefix of the address, which determines the range of IP addresses that fall within the CIDR block.

VPC CIDR Block: When creating a VPC, you specify an IP range for it in CIDR notation, such as 10.0.0.0/16. This CIDR block defines the total range of IP addresses available within the VPC.

Subnet CIDR Blocks: Each subnet within a VPC has its own CIDR block, which is a subset of the VPC’s CIDR block. For example, if the VPC CIDR block is 10.0.0.0/16, a subnet might use a CIDR block of 10.0.1.0/24, allowing for up to 256 IP addresses within that subnet.

CIDR notation provides flexibility in IP address allocation by allowing users to specify different subnet sizes based on their application needs.

# Subnet

A subnet is a subdivision of an Amazon VPC’s IP address range. Each subnet resides within a specific Availability Zone, providing a way to logically group resources and manage traffic flow within a VPC. Subnets can be designated as either public or private based on their access to the internet.

Public Subnet: A public subnet is connected to an Internet Gateway, allowing resources within it to communicate with the internet. This type of subnet is typically used for resources that require internet access, like web servers.

Private Subnet: A private subnet does not have a route to the Internet Gateway, so resources within this subnet are isolated from direct internet access. Private subnets are commonly used for backend resources, such as databases or application servers.

Subnets enable fine-grained control over how resources within a VPC are grouped and accessed, making it easier to apply different security and routing policies based on the purpose of each subnet.


