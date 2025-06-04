Ablauf wenn ein DHCP verwendet wird (statefull oder stateless):
1. Host sendet RS message
2. Router antwortet mit RA
3. Host sendet DHCPv6 SOLICIT message
4. DHCPv6 antwortet mit ADVERTISE message
5. Antwort von Host zu DHCP
6. DHCP sendet Reply
7. 
=> Host zu DHCP = UDP 546, DHCP zu Host = UDP 547

Bei Stateless wird "nur" Zusatinformation beim DHCP angefragt.

## Router als DHCP Server konfigurieren
## Stateless-DHCP-Server
```
R1(config)# ipv6 unicast-routing
R1(config)# ipv6 dhcp pool POOL-NAME
R1(dhcp-config)#network NETWORK
R1(dhcp-config)#default-router ROUTER
R1(dhcp-config)#dns-server DNS
R1(config-if)#ipv6 dhcp pool POOL-NAME
```

## DHCP-Client

```
R1(config)# ipv6 unicast-routing
R1(config-if)# ipv6 enable
R1(config-if)# ipv6 address autoconfig/dhcp #auto => statless
```
## Stateful-DHCP-Server
```
R1(config)# ipv6 unicast-routing
R1(config)# ipv6 dhcp pool POOL-NAME
R1(dhcp-config)# Statefull-Options here
R1(config-if)# ipv6 dhcp pool POOL-NAME
```

## Relay-Agent
```
R1(config-if)# ipv6 dhcp relay destiatnion IPV6 EGRESS-INT
```
## Verification
```
R1# show ipv6 dhcp pool
R1# show ipv6 dhcp binding
R1# show ipv6 dhcp interface
R1# show ipv6 dhcp pool
```