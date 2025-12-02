# IP-Adressplan - Laboration 3

## Loopbacks

| Enhet | Interface | IP-adress | Beskrivning |
|-------|-----------|-----------|-------------|
| SP1 | Lo0 | 1.1.1.1/32 | Router ID |
| SP2 | Lo0 | 2.2.2.2/32 | Router ID |
| LF1 | Lo0 | 3.3.3.3/32 | Router ID |
| LF2 | Lo0 | 4.4.4.4/32 | Router ID |

## Fabric-länkar (Area 0)

| Länk | Interface A | IP A | Interface B | IP B | Beskrivning |
|------|-------------|------|-------------|------|-------------|
| SP1-SP2 | Et1 | 10.0.10.1/30 | Et1 | 10.0.10.2/30 | Spine-to-Spine |
| SP1-LF1 | Et2 | 10.0.0.1/30 | Et4 | 10.0.0.2/30 | Fabric link |
| SP1-LF2 | Et3 | 10.0.1.1/30 | Et1 | 10.0.1.2/30 | Fabric link |
| SP2-LF1 | Et3 | 10.0.3.1/30 | Et1 | 10.0.3.2/30 | Fabric link |
| SP2-LF2 | Et2 | 10.0.4.1/30 | Et3 | 10.0.4.2/30 | Fabric link |

## Client Networks

| Enhet | Interface | IP-adress | Nätverk | OSPF Area | Summering |
|-------|-----------|-----------|---------|-----------|-----------|
| LF1 | Et2 | 10.10.10.1/24 | CLI-A | Area 10 | 10.10.0.0/16 |
| LF1 | Et3 | 10.10.11.1/24 | MON | Area 10 | 10.10.0.0/16 |
| LF2 | Et2 | 10.20.20.1/24 | CLI-B | Area 20 | 10.20.0.0/16 |

## Klienter

| Enhet | Interface | IP-adress | Gateway | Beskrivning |
|-------|-----------|-----------|---------|-------------|
| CLI-A | ens4 | 10.10.10.10/24 | 10.10.10.1 | Test client A |
| CLI-B | ens4 | 10.20.20.10/24 | 10.20.20.1 | Test client B |
| MON | ens4 | 10.10.11.50/24 | 10.10.11.1 | Monitoring node |

## Internet Edge

| Enhet | Interface | IP-adress | Beskrivning |
|-------|-----------|-----------|-------------|
| SP1 | Et4 | 192.168.122.134/24 (DHCP) | NAT1 connection |
| SP2 | Et4 | - | NAT2 connection |
