IPv6MESH <a href="https://flattr.com/submit/auto?user_id=renne&url=http://ipv6mesh.eu&title=IPv6MESH&language=C99&tags=github&category=software"><img src="http://api.flattr.com/button/flattr-badge-large.png" height="24em" width="16%"/></a>
========

**IPv6MESH** is a mesh network extension for the Internet Protocol 6.


##**Features:**
* Security based on **4096-bit RSA** key-pairs
* **C**ryptographically **G**enerated **E**ndpoint **I**dentifiers **(CGEIDs)**
  * 32-bit IANA prefix
  * 96-bit SHA-2 HASH of RSA public key
  * Compatibel with 128-bit IPv6-addresses
  * RSA-based authentication
  * **Decentralized ad-hoc generation**
  * Can be exchanged between users via QR-code, NFC, VCards, etc.
* End-2-End payload encryption
  * RSA exchange of random stream-cipher key
  * AES-256 stream-cipher
  * Perfect Forward Secrecy
* D1HT routing table
  * UDP protocol
  * Bootstrapping
    * IPv6MESH nodes known via Neighbour Discovery Protocol
    * IPv4/IPv6 anycast address
  * CGEID-based index (prevents Sybil attacks)
  * Record type for CGEID/RSA public key tupel
  * Record type for CGEIDs of point-2-point mesh neighbours and IPv4/IPv6 adresses of routers
  * RSA-signed records (prevents Spartacus attacks)
  * BGP replacement
  * Survives (global) BGP-blackout
  * Survives (global) DNS-blackout
  * STUN replacement
* Conventional IPv6 routing for LANs
  * CGEID creation/authorisation and payload encryption on ipv6mesh router
  * CGEID provisioning for conventional IPv6 devices via DHCPv6
* Conventional BGP-based IPv6 routing
  * All ipv6mesh nodes with conventional IPv6 connectivity are egress routers
  * All ipv6mesh nodes with conventional IPv6 connectivity AND BGP announcements (32-bit IANA prefix -> IPv6 address) are ingress routers
  * Any BGP operator can publish BGP routes of ingress nodes by scanning the D1HT routing table
  * Tunneling via conventional IPv4/IPv6 between ipv6mesh border nodes or nodes without direct connection to the mesh network
* Implemetation of onion routing depends on performance
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
