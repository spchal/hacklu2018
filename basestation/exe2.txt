In the previous exercise, we got familiar with the basic configuration of the osmo-nitb that consists of osmo-bsc, ggsn and sgsn. 
In this section, we get into the next step of running all the components.

Go to the run folder and start the below scripts in the right order:
1. gprs_network.sh
Within this script, you will notice than an iptable rule is made to masquerade all traffic in the interface with internet. 
2. start_ggsn.sh
3. start_sgsn.sh
4. start_bsc.sh
5. start_web.sh

Test if everything is running properly.
Find the port numbers on which each service is running and telnet to the services. 
You can get shells on the service running instance which can be used for further testing of the configuration as well as making live changes. 




