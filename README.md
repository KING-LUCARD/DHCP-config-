<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>DHCP Configuration - Cisco Packet Tracer</title>
</head>
<body>

<h1>DHCP Configuration Using Cisco Packet Tracer</h1>

<h2>Project Overview</h2>
<p>
This project demonstrates how to configure <strong>Dynamic Host Configuration Protocol (DHCP)</strong> 
in Cisco Packet Tracer to automatically assign IP addresses to client devices within a LAN.
</p>

<ul>
    <li>IP Address</li>
    <li>Subnet Mask</li>
    <li>Default Gateway</li>
    <li>DNS Server</li>
</ul>

<hr>

<h2>Network Topology</h2>

<h3>Devices Used:</h3>
<ul>
    <li>1 Router (Cisco 2911 / 1941)</li>
    <li>1 Switch (2960)</li>
    <li>Multiple PCs (Clients)</li>
    <li>Straight-through cables</li>
</ul>

<h3>Network Addressing Scheme:</h3>
<table border="1">
    <tr>
        <th>Device</th>
        <th>IP Address</th>
    </tr>
    <tr>
        <td>Router (Gateway)</td>
        <td>192.168.1.1</td>
    </tr>
    <tr>
        <td>DHCP Pool Range</td>
        <td>192.168.1.100 – 192.168.1.200</td>
    </tr>
    <tr>
        <td>Subnet Mask</td>
        <td>255.255.255.0</td>
    </tr>
</table>

<hr>

<h2>Network Topology Screenshot</h2>
<p><strong>Replace the image file below with your actual Packet Tracer screenshot.</strong></p>

<img src="topology.png" alt="Cisco Packet Tracer DHCP Topology Screenshot" width="600">

<hr>

<h2>Step-by-Step DHCP Configuration</h2>

<h3>Step 1: Configure Router Interface</h3>
<pre>
enable
configure terminal
interface gigabitEthernet 0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
</pre>

<h3>Step 2: Exclude Reserved IP Addresses</h3>
<pre>
ip dhcp excluded-address 192.168.1.1 192.168.1.99
</pre>

<h3>Step 3: Create DHCP Pool</h3>
<pre>
ip dhcp pool LAN_POOL
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8
exit
</pre>

<hr>

<h2>Configure PCs to Use DHCP</h2>
<ol>
    <li>Click on PC</li>
    <li>Go to Desktop</li>
    <li>Click IP Configuration</li>
    <li>Select DHCP</li>
</ol>

<hr>

<h2>Verification</h2>

<h3>On Router:</h3>
<pre>
show ip dhcp binding
show ip dhcp pool
</pre>

<h3>On PC:</h3>
<pre>
ipconfig
ping 192.168.1.1
</pre>

<hr>

<h2>Project Objectives</h2>
<ul>
    <li>Configure router as DHCP server</li>
    <li>Automatically assign IP addresses</li>
    <li>Verify DHCP bindings</li>
    <li>Test network connectivity</li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>
This project demonstrates practical implementation of DHCP in a simulated LAN environment 
using Cisco Packet Tracer. The router dynamically assigns IP addresses to connected devices, 
ensuring efficient and automated network configuration.
</p>

</body>
</html>
