# LLMNR-POISONING

What is LLMNR?
LLMNR is a protocol that allows both IPv4 and IPv6 hosts to perform name resolution for hosts on the same local network without requiring a DNS server or DNS configuration.

When a host’s DNS query fails (i.e., the DNS server doesn’t know the name), the host broadcasts an LLMNR request on the local network to see if any other host can answer.

LLMNR is the successor to NetBIOS.  NetBIOS (Network Basic Input/Output System) is an older protocol that was heavily used in early versions of Windows networking. NBT-NS is a component of NetBIOS over TCP/IP (NBT) and is responsible for name registration and resolution.  Like LLMNR, NBT-NS is a fallback protocol when DNS resolution fails. It allows local name resolution within a LAN.

<p align="center">
<b>Root User</b>
<br/>
  <img src="https://github.com/BunNYb8989/LLMNR/blob/main/llmnr.png" height="40%" width="40%"/>
<br/>
<br/>
</p>

1.Query: When a device on the network needs to resolve the name of another device, it sends out an LLMNR query.
This query is typically a multicast message sent to the link-local multicast address (224.0.0.252 for IPv4 and FF02::1:3 for IPv6).

2.Broadcasting: The LLMNR query is broadcasted to all devices on the local network segment.

3.Response: If the queried device recognizes its name and is present on the network, it responds directly to the querying device with its IP address.

4.Resolution: The querying device receives the response and can then communicate directly with the target device using its IP address.

 # IN LINUX TERMINAL  <p align="center">
<b>Root User</b>
<br/>
  <img src="https://github.com/BunNYb8989/LLMNR/blob/main/kali.gif" height="5%" width="5%"/>
<br/>
<br/>
</p>

<p align="center">
<b>Root User</b>
<br/>
  <img src="https://github.com/BunNYb8989/LLMNR/blob/main/responder.png" height="40%" width="40%"/>
<br/>
<br/>
</p>

Responder.py with the appropriate parameters to start listening for LLMNR queries and poison responses.

sudo python3 /usr/share/doc/python3-impacket/examples/Responder.py -I eth0

```
sudo reponder -I eth0 -v
```

Replace eth0 with the interface connected to the network.
This command starts Responder.py, which will listen for LLMNR (and other) queries on the specified network interface (eth0 in this case).
When it detects an LLMNR query, it will respond with a malicious response, potentially redirecting traffic or capturing sensitive information.
