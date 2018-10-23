## Prototyping & Evaluation

---------------------

#### _* Hypothesis_

Measure the response time of the tree servers located in different parts of the world.

http://139.59.132.185:8080

http://192.81.216.124:8080

http://128.199.180.131:8080

---------------------

#### _* Plan_

1. Find the location of the servers.
2. Distance from request to the servers location.
3. Measure latency between my location and the server.

---------------------

#### _* Execute the experiment._

1. To find out where the servers are located I used https://www.iplocation.net/

```
IP Address:
139.59.132.185
Country:
Germany
City:
Frankfurt am Main
```
```
IP Address:
192.81.216.124
Country:
United States
City:
North Bergen
```
```
IP Address:
128.199.180.131
Country:
Singapore
City:
Singapore
```

2. To calculate distance, I am using https://www.distancecalculator.net

```
Copenhagen > Frankfurt am Main = 671.98 km
```
```
Copenhagen > North Bergen = 6188.02 km
```
```
Copenhagen > Singapore = 9972.99 km
```

3. Ping IP addresses and measure response times.

Germany:
```terminal
➜  ~ ping 139.59.132.185
PING 139.59.132.185 (139.59.132.185): 56 data bytes
64 bytes from 139.59.132.185: icmp_seq=0 ttl=54 time=20.638 ms
64 bytes from 139.59.132.185: icmp_seq=1 ttl=54 time=23.658 ms
64 bytes from 139.59.132.185: icmp_seq=2 ttl=54 time=23.000 ms
```

United States:
```terminal
➜  ~ ping 192.81.216.124
PING 192.81.216.124 (192.81.216.124): 56 data bytes
64 bytes from 192.81.216.124: icmp_seq=0 ttl=48 time=95.891 ms
64 bytes from 192.81.216.124: icmp_seq=1 ttl=48 time=94.741 ms
64 bytes from 192.81.216.124: icmp_seq=2 ttl=48 time=95.856 ms
```

Singapore:
```terminal
➜  ~ ping 128.199.180.131
PING 128.199.180.131 (128.199.180.131): 56 data bytes
64 bytes from 128.199.180.131: icmp_seq=0 ttl=38 time=276.836 ms
64 bytes from 128.199.180.131: icmp_seq=1 ttl=38 time=386.634 ms
64 bytes from 128.199.180.131: icmp_seq=2 ttl=38 time=276.049 ms
```

---------------------

#### _* Evaluate the experiment._

The further away the server is located, the higher the ping times is.

---------------------

#### _* Discussion._

 What is measured?

 How is it measured?

 What could influence results?
