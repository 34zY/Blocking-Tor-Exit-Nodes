# Blocking-Tor-Exit-Nodes
This repository is dedicated to defend against Malware who uses proxy from TOR Exit Nodes

IPTABLE rule ; 
```
ipset create tor-nodes iphash
curl -sSL "https://www.dan.me.uk/torlist/?ip=$(curl icanhazip.com)" |  sed -e '/^#/d' -e '/:/d' | while read IP; do
  ipset -q -A tor-nodes $IP
done
```
