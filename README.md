# LLMNR-POISONING

What is LLMNR?
LLMNR is a protocol that allows both IPv4 and IPv6 hosts to perform name resolution for hosts on the same local network without requiring a DNS server or DNS configuration.

When a host’s DNS query fails (i.e., the DNS server doesn’t know the name), the host broadcasts an LLMNR request on the local network to see if any other host can answer.

LLMNR is the successor to NetBIOS.  NetBIOS (Network Basic Input/Output System) is an older protocol that was heavily used in early versions of Windows networking. NBT-NS is a component of NetBIOS over TCP/IP (NBT) and is responsible for name registration and resolution.  Like LLMNR, NBT-NS is a fallback protocol when DNS resolution fails. It allows local name resolution within a LAN.
