Sniff the traffic

If the authentication policy in your osmo-bsc is not 'accept-all', you will have to manually accept the authentication request from a random SIM card.
Connect to the web service from your browser to see the incoming authentication requests to your base station. 

You can also see the logs of the osmo-bsc service to see the IMSI of the registered subscriber. 

The interface for sniffing is tun0. 

$ tcpdump -i tun0 -w my_name.pcap







