## Description:

Docker container bridge (dcontainerbridge) is an adaptive, lightweight, and transparent tool used with docker containers to improve network connectivity. It is utilized to attach another network interface to the running docker container. Which allows it to run multiple compute services with different IPs or can be accessed from outside docker network (via other LAN/WAN). The tool can also detach the added interface transparently while the container is running without any change of the basic docker network connectivity. 

dcontainerbridge adapts the network stack of the running container and its hosting machine to add another network interface to the running container. This is achieved via creating a network bridge on the hosting machine and a virtual ethernet pair.One virtual veth is added to the container while the other is added to the bridge. The bridge will also include the network interface of the hosting machine. 


Download and use dcontainerbridge tool:

   	$ git clone https://github.com/aneesalnajjar/dcontainerbridge.git
	$ cd dcontainerbridge
   	$ sudo chmod 774 dcontainerbridge.
   	$ ./dcontainerbridge OPTIONS [ARGs]
   
	   
	   
    OPTIONS
      --create, -c	Create a network interface attached to the host.
			ARGs
			<host-name> <host-intf.> <container-name> <attached intf. IP>

      --remove, -r	Remove the attached network interface from the container.
			ARGs
			<host-name> <host intf.> <container-name> 

      --version, -v	The current version of dcontainerbridge

      --help, -h	dcontainerbridge manual page
	  
	  
	  
	EXAMPLES:
		./dcontainerbridge --create mndock1 mndock1-eth0 container-x 172.16.0.10
		./dcontainerbridge --remove mndock1 mndock1-eth0 container-x
		./dcontainerbridge --version 
		./dcontainerbridge --help


### Developer:

Anees Al-Najjar,

Oak Ridge National Laboratory (ORNL), Oak Ridge, TN, 37830, USA

alnajjaram@ornl.gov

**To site this tool, please refer to the following reference**

@INPROCEEDINGS{9524993,
  author={Al-Najjar, Anees and Rao, Nageswara S. V. and Imam, Neena and Naughton, Thomas and Hitefield, Seth and Sorrillo, Lawrence and Kohl, James and Elwasif, Wael and Bilheux, Jean-Christophe and Bilheux, Hassina and Boehm, Swen and Kincl, Jason},
  booktitle={2021 IEEE 46th Conference on Local Computer Networks (LCN)}, 
  title={Virtual Framework for Development and Testing of Federation Software Stack}, 
  year={2021},
  volume={},
  number={},
  pages={323-326},
  doi={10.1109/LCN52139.2021.9524993}}
