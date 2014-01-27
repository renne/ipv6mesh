IPv6MESH <a href="https://flattr.com/submit/auto?user_id=renne&url=http://ipv6mesh.eu&title=IPv6MESH&language=C99&tags=github&category=software"><img src="http://api.flattr.com/button/flattr-badge-large.png" height="24em" width="16%"/></a>
========

**IPv6MESH** is a community project founded on 01/01/2014 by Rene Bartsch to develop and standardize a mesh network extension for the Internet Protocol 6 (OSI Layer 3). Every IPv6MESH node will generate it's cryptographically secured IPv6 addresses (CGEIDs) and connections to neighbour nodes ad-hoc which allows to deploy a large number of nodes in a IPv6MESH cloud automagically.

**IPv6MESH** can be used to set up emergency communication networks, vehicle-2-vehicle communication (car-2-car, ship-2-ship, satellite-2-satellite), can close gaps in networks by e.g. integrating nodes into reflector posts, streetlights, trees, moored buoys or balloons, geostationary satellites or just serve as a community network.


##**Planned features:**
* **Proof-of-concept implementation based on TUN device**
* **Filing of IETF Internet Draft**
* **Security based on *4096-bit RSA* key-pairs**
* ***C*ryptographically *G*enerated *E*ndpoint *ID*entifiers (*CGEIDs*)**
  * 32-bit IPv6 IANA prefix (XXXX:XXXX::0/32)
  * 96-bit SHA-2 hash of RSA public key as interface identifier
  * Compatibel with 128 bit IPv6-addresses
  * RSA based authentication
  * **Decentralized ad-hoc generation**
  * Import/export/backup (CGEID, public/private key) via PKCS12 files named "&lt;CGEID&gt;.p12"
  * CGEID can be exchanged between users via QR code, NFC, VCards, etc.
  * IPv6MESH router operators don't have to provide any public IPv6 addresses to users/hosts
* **Privacy**
  * Pseudonimyzed IP addresses (CGEIDs)
    * static CGEIDs for incoming connections
      * Preferred Lifetime:          1 second  (some OS do not accept a zero value)
      * Valid Lifetime:     4294967295 seconds (infinite)
    * temporary CGEIDs for outgoing connections
      * Preferred Lifetime:      86700 seconds (24h + 5 minutes overlapping)
      * Valid Lifetime:         172800 seconds (48h)
      * Exchange at 00:00 o'clock UTC
  * Onion routing depends on performance
  * End-2-End payload encryption
    * Exchange of random symmetric stream cipher key by asymmetric RSA key pair
    * AES256 stream cipher
    * Perfect Forward Secrecy
* **Distributed HashTable for host/node/routing information**
  * CGEID-based index (prevents Sybil attacks)
  * RSA-signed records (prevents Spartacus attacks)
  * UDP transport 
  * Bootstrapping
    * CGEIDs known via Neighbour Discovery Protocol
    * IPv4/IPv6 anycast address
  * Record types of a IPv6MESH node
    * CGEID/RSA public key tupel for authentication
    * Point-2-Point IPv6MESH neighbours
    * Public IPv4/IPv6 addresses
    * Alternate CGEIDs (load-balancing, redundancy)
    * NAT64 support
    * Geographic position
      * Distributed network coverage map
      * Positioning of laser communication terminals
    * Reverse Domain Name System records (PTR)
  * Replaces and survives (global) blackout of
    * BGP
    * STUN servers
    * LISP map-servers
    * LISP map-resolvers
    * CGEID zone reverse DNS servers
* **Routing algorithm**
  * ??? (evaluate Hyperboria)
* **Compatibility with IPv6 LANs**
  * CGEID creation/authorisation/payload encryption on IPv6MESH default gateway
  * CGEID provisioning of conventional IPv6 devices via DHCPv6
* **Compatibility with BGP-routed internet**
  * IPv6 ingress routing via anycast address
    * BGP: &lt;CGEID prefix&gt;::0/32 -> &lt;CGEID prefix&gt;::1/128 -> IPv6 addresses of all reliable IPv6MESH nodes
  * All IPv6MESH nodes with IPv6 connectivity are egress border routers
  * IPv4 anycast address
    * BGP: XXX.XXX.XXX.XXX/32 -> IPv4 addresses of all reliable IPv6MESH nodes
  * Any BGP operator can scan the D1HT and publish BGP routes via e.g. Quagga extension
  * Optional NAT64 gateway support
    * Provides connectivity to IPv4 hosts
    * Public IPv4 addresses necessary on NAT64 gateway
    * Can be registered as internet service provider to avoid german "Störerhaftung"
  * Reverse DNS of CGEID prefix
    * All nodes with IPv4/IPv6 connectivity are authoritative anycast nameservers
    * UDP only
    * Rerverse DNS glue records
      * IPv6: &lt;reversed CGEID prefix&gt;.ip6.arpa. 86400 NS &lt;IPv6 anycast IP&gt;
      * IPv4: &lt;reversed CGEID prefix&gt;.ip6.arpa. 86400 NS &lt;IPv4 anycast IP&gt;
* **LISP-tunneling**
  * Connectivity between IPv6MESH clouds/isolated nodes
  * CGEIDs are LISP EIDs
  * IPv4/IPv6 addresses are LISP RLOCs
  * CGEID -> RLOC mapping via DHT
* **Physical connectivity**
  * Wires and radio links can be DIY-installed between homes
  * Wired communication
    * IEEE 802.3 Clause 38 (1000Base-SX/LX) preferred
    * IEEE 802.3 Clause 40 (1000Base-T) can be used with surge protection
  * Radio communication
    * IEEE 802.11ac preferred (802.11h necessary in most countries)
    * IEEE 802.11ad as next generation (lobbyists needed to get reserved frequency range)
    * Reduction of electromagnetic interferences on other IPv6MESH nodes
      * Transmit Power Control
      * 2-dimensional beamforming
    * Unencrypted (B)SSID "IETFRFC&lt;rfc number&gt;" ("ipv6mesh.eu" until formal release of RFC)
  * Laser Communication Terminals
* **No support** for *Global No Such Agency Backup Service* **;-)** 
* ***GPLv2 license*** (Flattr button/Bitcoin address must not be manipulated)

##**Contact**
Email: **webmaster** AT **ipv6mesh.eu**

##**Contribute**
* ***Support project IPv6MESH*** (hardware, internet connectivity, domains, administrative costs, ...) via Flattr by starring on GitHub or via Bitcoin address 1FqEeuW54veJzcuyKbEUYrqjTNsbTYVLKr
* Test, register bugs or leave a feature request or proposal at https://github.com/renne/ipv6mesh/issues
* Contribute to the Wiki at https://github.com/renne/ipv6mesh/wiki
* Fork, write code and make a pull request 
  * Coding conventions: https://github.com/renne/ipv6mesh/wiki/Coding-conventions
