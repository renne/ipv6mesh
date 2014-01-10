IPv6MESH <a href="https://flattr.com/submit/auto?user_id=renne&url=http://ipv6mesh.eu&title=IPv6MESH&language=C99&tags=github&category=software"><img src="http://api.flattr.com/button/flattr-badge-large.png" height="24em" width="16%"/></a>
========

**IPv6MESH** is a mesh network extension for the Internet Protocol 6 (OSI Layer 3). Every node generates IPv6 addresses ad-hoc and connects to it's neighbour nodes which allows to deploy large number of nodes automagically.

**IPv6MESH** can be used to set up emergency communication networks, vehicle-2-vehicle communication (car-2-car, ship-2-ship), can close gaps in networks by e.g. integrating nodes into reflector posts or just serves as a community network.


##**Features:**
* Security based on **4096-bit RSA** key-pairs
* **C**ryptographically **G**enerated **E**ndpoint **I**dentifiers **(CGEIDs)**
  * 32-bit IPv6 IANA prefix (XXXX:XXXX::0/32)
  * 96-bit SHA-2 HASH of RSA public key as interface identifier
  * Compatibel with 128-bit IPv6-addresses
  * RSA-based authentication
  * **Decentralized ad-hoc generation**
  * Can be exchanged between users via QR-code, NFC, VCards, etc.
* End-2-End payload encryption
  * Exchange of random symmetric stream-cipher key by asymmetric RSA key pair
  * AES-256 stream-cipher
  * Perfect Forward Secrecy
* D1HT routing table
  * UDP transport
  * Bootstrapping
    * IPv6MESH nodes known via Neighbour Discovery Protocol
    * IPv4/IPv6 anycast address
  * CGEID-based index (prevents Sybil attacks)
  * Record type for CGEID/RSA public key tupel
  * Record type for CGEIDs of point-2-point mesh neighbours and IPv4/IPv6 adresses of routers
  * Record type for alternate CGEIDs (load-balancing, redundancy)
  * Record type for NAT64 proxy routers
  * Record type for geographic position of IPv6MESH nodes to provide network coverage map
  * RSA-signed records (prevents Spartacus attacks)
  * BGP replacement
  * Survives (global) BGP-blackout
  * Survives (global) DNS-blackout
  * STUN replacement
* Compatibility with IPv6 LANs
  * CGEID creation/authorisation and payload encryption on IPv6MESH router
  * CGEID provisioning for conventional IPv6 devices via DHCPv6
* Compatibility with BGP-routed Internet
  * All IPv6MESH nodes with BGP-based IPv6 connectivity are ingress/egress border routers
  * Ingress routing via Anycast addresses
    * IPv6: XXXX:XXXX::0/32    -> XXXX:XXXX::1/128 -> IPv6 addresses of IPv6MESH nodes
    * IPv4: XXX.XXX.XXX.XXX/32 ->                     IPv4 addresses of IPv6MESH nodes
    * Any BGP operator can publish BGP routes by scanning the D1HT routing table
* Tunneling between IPv6MESH clouds/lonely nodes via BGP-routed IPv4/IPv6 protocol
* Implementation of onion routing depends on performance
* Filing of IETF Internet Draft planned when IPv6MESH scales well
* **No support** for *Global No Such Agency Backup Service* **;-)** 
* Hardware/OS-independent
* ***GPLv2 license*** (Flattr button/Bitcoin address must not be manipulated)
* Coding conventions: https://github.com/renne/ipv6mesh/wiki/Coding-conventions
* Feature requests and bugs: https://github.com/renne/ipv6mesh/issues
* Wiki: https://github.com/renne/ipv6mesh/wiki

##**Contact**
Email: webmaster *AT* ipv6mesh.eu

##**Contribute**
* You can ***support project IPv6MESH*** (hardware, internet connectivity, domains, administrative costs, ...) via Flattr by starring on GitHub
* Fork, write code and make a pull request
* Test and register bugs at https://github.com/renne/ipv6mesh/issues
* Contribute to the Wiki at https://github.com/renne/ipv6mesh/wiki
