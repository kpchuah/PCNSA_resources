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
**Routing Preference**
When two routing subnets / CIDRs coinicide, the longest match is preferred. For instance:
10.1.1.0/24 </br>
10.1.1.16/25 [preferred] </br>
