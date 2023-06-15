Each service is forced to go out using its envoy proxy.
The rule is: All that comes from NF IP is forced to go to envoy proxy IP.

```
# AMF
sudo iptables -t nat -A OUTPUT -s 127.0.0.18 -j DNAT --to-destination 127.0.1.18

# AUSF
sudo iptables -t nat -A OUTPUT -s 127.0.0.9 -j DNAT --to-destination 127.0.1.9

# NSSF
sudo iptables -t nat -A OUTPUT -s 127.0.0.31 -j DNAT --to-destination 127.0.1.31

# UDM
sudo iptables -t nat -A OUTPUT -s 127.0.0.3 -j DNAT --to-destination 127.0.1.3

# UDR
sudo iptables -t nat -A OUTPUT -s 127.0.0.4 -j DNAT --to-destination 127.0.1.4

# PCF
sudo iptables -t nat -A OUTPUT -s 127.0.0.7 -j DNAT --to-destination 127.0.1.7

# SMF
sudo iptables -t nat -A OUTPUT -s 127.0.0.2 -j DNAT --to-destination 127.0.1.2



# Get IPTables rules

sudo iptables -t nat -L OUTPUT --line-numbers

# Delete IPTables rule
sudo iptables -t nat -D OUTPUT 1
```