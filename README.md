# Blocking-Tor-Exit-Nodes
This repository is dedicated to defend against Malware who uses proxy from TOR Exit Nodes

IPTABLE rule loop ; 
```
ipset create tor-nodes iphash
curl -sSL "https://www.dan.me.uk/torlist/?ip=$(curl icanhazip.com)" |  sed -e '/^#/d' -e '/:/d' | while read IP; do
  ipset -q -A tor-nodes $IP
done
```

References :

https://www.dan.me.uk/torlist/<br>
https://gist.github.com/jkullick/62695266273608a968d0d7d03a2c4185<br>
https://torproject.org<br>
https://blog.torproject.org/changes-tor-exit-list-service/<br>
