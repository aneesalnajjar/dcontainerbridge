Discription:

Containerbridge is an adaptive, lightweight, and transparent tool used with docker containers to improve the network connectivity. It is utilized to attach another network interface to the running docker container. Which allows it runing multiple compute services with different IPs or can be accessed from outside docker network (via other LAN/WAN). The tool can also dettach the added interface transparently while the container is runing without any chnage of the basic docker network connectivity. 

Containerbridge adapts the network stack of the running container and its hosting machine to add another network interface to the running container. This is achieved via creating a network bridge on the hosting machine and a virtual ethernet pair.One virtual veth is added to the container while the other is added to the bridge. The bridge will also include the network interface of the hosting machine. 


How to use Containerbridge tool:

   1- Download the tool.
   
   2- sudo chmod 774 containerbridge.
   
   3- ./containerbridge OPTIONS [ARGs]
   
	   
	   
    OPTIONS
      --create, -c	Create a network interface attached to the host.
			ARGs
			<host-name> <host-intf.> <container-name> <attached intf. IP>

      --remove, -r	Remove the attached network interface form the contianer.
			ARGs
			<host-name> <host intf.> <container-name> 

      --version, -v	The current version of containerbridge

      --help, -h	containerbridge manual page
	  
	  
	  
	EXAMPLES:
		./containerbridge --create mndock1 mndock1-eth0 container-x 172.16.0.10
		./containerbridge --remove mndock1 mndock1-eth0 container-x
		./containerbridge --version 
		./containerbridge --help


Developer:

Anees Al-Najjar,

Postdoctorol Research Associate,

Oak Ridge National Laboratory (ORNL), Oak Ridge, TN, 37830, USA

alnajjaram@ornl.gov
