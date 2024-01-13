# Blocking-Tor-Exit-Nodes
This repository is dedicated to defend against Malware who uses proxy from TOR Exit Nodes

IPTABLE rule loop ; 
```
ipset create tor-nodes iphash
curl -sSL "https://www.dan.me.uk/torlist/?ip=$(curl icanhazip.com)" |  sed -e '/^#/d' -e '/:/d' | while read IP; do
  ipset -q -A tor-nodes $IP
done
```

Reference :

https://www.dan.me.uk/torlist/
https://gist.github.com/jkullick/62695266273608a968d0d7d03a2c4185
https://torproject.org
