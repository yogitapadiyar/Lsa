# Lsa
# Practical no 1
Install DHCP Server in Ubuntu 16.04
Dynamic Host Configuration Protocol (DHCP) is a network protocol that is used to enable host computers to be automatically assigned IP addresses and related network configurations from a server.

Steps to install dhcp server in Ubuntu 16.04:-
1.Open Terminal and run the following command to install DHCP server:
sudo apt-get install isc-dhcp-server
2.Now our dhcp server is installed now we have to configure it.
3.The default configuration file of dhcp server is /etc/default/isc-dhcp-server.
4.To Comfigure , edit /etc/default/isc-dhcp-server configuration file:
sudo vi /etc/default/isc-dhcp-server.
5.Assign the network interface:
INTERFACES="eth0".
6.If you have more than one interfaces, mention them with spaces, for exampleb eth0 eth1.
7.Save and close the file.
Then, edit dhcpd.conf file,
sudo vi /etc/dhcp/dhcpd.conf.
Modify it as shown below. Replace the domain name with your own values.
Enter the domain name and domain-name-servers:
option domain-name "mohdubaid011.lan";
option domain-name-servers ubuntuserver.mohdubaid011.lan;
8.Configuring DHCP in Ubuntu 16.04:-
Then we must edit in the following
sudo vi /etc/dhcp/dhcpd.conf
There we must enter the respective dhcp values we must add the following lines inthe required configuration.
subnet 192.168.0.1 netmask 255.255.255.0 {

range 192.168.0.10 192.168.0.40;

option domain-name-servers 8.8.8.8, 4.4.4.4;

option domain-name "solvetic";

option routers 192.168.0.1;

option broadcast-address 192.168.0.255;

default-lease-time 600;

max-lease-time 7200;

}
9.Once these values are configured we will proceed to restart the isc-dhcp-server service using the following command:
sudo systemctl restart isc-dhcp-server
10.Start and stop the isc-dchp-server service
The commands to start and stop this service are:
Start service:-sudo systemctl start isc-dhcp-server
Stop service:-sudo systemctl stop isc-dhcp-server

# Practical no 2
Add a User in a kali linux
Command :- adduser username
Network Setting In Kali Linux
IP Address
Command :- sudo ifconfig -a
IP address and Netmask Network Configuration
Command:- sudo ifconfig eth0 192.168.1.10 netmask 255.255.255.0
Configure Services In Kali Linux
Command :- service ssh start
Command :- ssh username@hostname
Basic Command To Run , Enable , Start and Stop Services
Command :- systemctl [command] [service_name]
To stop and restart the service in Linux, use the command:
Command :- sudo systemctl restart SERVICE_NAME
Command :- sudo systemctl stop SERVICE_NAME
To Enable Services At Boot
Command :- sudo systemctl enable SERVICE_NAME
To display the list of services which are running In Kali Linux
Command :- sudo systemctl -t=service --state=running
Sudo settings
Command :- sudo apt install -y software_name
Any Command Which Are Used With Sudo Give A User A Super User Advantage.
