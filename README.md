IPv6MESH <a href="https://flattr.com/submit/auto?user_id=renne&url=http://ipv6mesh.eu&title=IPv6MESH&language=C99&tags=github&category=software"><img src="http://api.flattr.com/button/flattr-badge-large.png" height="24em" width="16%"/></a>
========

**IPv6MESH** is a mesh network extension for the Internet Protocol 6.


##**Features:**
* Security based on **4096-bit RSA** key-pairs
* **C**ryptographically **G**enerated **E**ndpoint **I**dentifiers **(CGEIDs)**
 * 32-bit IANA prefix
 * 96-bit SHA-2 HASH of RSA public key
 * Compatibel with IPv6-addresses
 * RSA-based authentication
 * **Decentralized ad-hoc generation**
 * Can be exchanged between users via QR-code, NFC, VCards, etc.
* End-2-End payload encryption
 * RSA exchange of random stream-cipher key
 * Perfect Forward Secrecy
 * AES-256 stream-cipher
* D1HT routing table
 * UDP protocol
 * CGEID-based index
 * Record type for CGEID/RSA public key tupel
 * Record type for CGEIDs of point-2-point mesh neighbours and IPv4/IPv6 adresses of routers
 * RSA-signed records
 * BGP replacement
 * Survives (global) BGP-blackout
 * Survives (global) DNS-blackout
 * STUN replacement
* Conventional BGP-based IPv6 routing
 * All mesh nodes are egress routers
 * All mesh nodes with BGP announcements are ingress routers
 * Any BGP operator can publish ingress nodes by scanning the D1HT routing table
 * Encrypted IPv4/IPv6 tunneling
    * NAT Traversal
    * TURN replacement
    * Nodes without mesh connectivity/mesh border nodes can tunnel the encrypted payload to each other
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
