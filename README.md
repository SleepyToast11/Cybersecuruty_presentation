# Intro
Here are the files and code used to do a final presentation in front of peers. This presentation orbits denials of service attacks and possible mitigation methods. These were performed in a local netwwork without external connection to insure that no possible outside repercutions were possible. 

The target was an apache server that served a simple one page static webpage running from a docker container at first . Afterwards, the target was updated to run 2 apache servers with 1 load-balancer server. 

The methods of attack were threefold: ICMP flood, SYN flood and slowloris. 
Firstly, ICMP flood was mitigated at the kernel level with a nethook module that prohibited any ICMP packet to reach the server. This did solved the issue at the local level, but was not realistic as these types of attacks usually try to overwhelm the connection at a lower layer of OSI. Preventing ICMP also prevents debugging possibility in the advent of a loss of connection, so that is also a consideration with this mitigation. Overall, this attack was more a proof of concept of the type of attack and the mitigation mostly a show of the power of modules and nethook.

Secondly, Syn flood attack was mitigated by reenabling to the default configuration of the tcp cookie.

Lastly, slowloris was partially mitigated using very harsh timeout values in the configuration of the servers to help fend off the fake website access. The values used were too low for any kind of real production environment, but since the attack was happening at a local level with essentially perfect connection leading to a very hard to mitigate attack.

For any question do hesitate to contact.
