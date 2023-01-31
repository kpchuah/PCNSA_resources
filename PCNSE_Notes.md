## IP Routing
The Administrative Distances assosiated with routing are:</br>
Routing Type --- Administrative Distance</br>
Connected ------- 0</br>
Static ---------- 10</br>
e BGP ----------- 20</br>
i OSPF ---------- 30</br>
e OSPF ---------- 110</br>
RIP ------------- 120</br>
i BGP ----------- 200</br>
</br>
In Palo Alto CLI, you can find this by the command `show routing summary`</br>
![image](https://user-images.githubusercontent.com/52063741/215765472-c81e058b-4877-4e4f-8075-a01a112d25d6.png) </br>
### Features
**Routing Preference**</br>
When two routing subnets / CIDRs coinicide, the longest match is preferred. For instance:</br>
10.1.1.0/24 </br>
10.1.1.16/25 [preferred] </br>
### Path Monitoring
When you Configure Path Monitoring for a __Static Route__, the firewall uses path monitoring to detect when the path to one or more monitored destination has gone down. The firewall can then reroute traffic using alternative routes. The firewall uses path monitoring for static routes much like path monitoring for HA or policy-based forwarding (PBF), as follows:
1. The firewall sends ICMP ping messages (heartbeat messages) to one or more monitored destinations that you determine are robust and reflect the availability of the static route.
2. If pings to any or all of the monitored destinations fail, the firewall considers the static route down too and removes it from the Routing Information Base (RIB) and Forwarding Information Base (FIB). 
3. If pings to any or all of the monitored destinations fail, the firewall considers the static route down too and removes it from the Routing Information Base (RIB) and Forwarding Information Base (FIB). The firewall continues to monitor the failed route. When the route comes back up, and (based on the Any or All failure condition) the path monitor returns to Up state, the preemptive hold timer begins. 
