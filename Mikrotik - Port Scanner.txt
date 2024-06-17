add action=drop chain=forward comment="Port Scanner" src-address-list=Block_PortScan
add action=add-src-to-address-list address-list=Block_PortScan address-list-timeout=2w chain=forward comment="Port scanner Add" protocol=tcp psd=21,3s,3,1
add action=add-src-to-address-list address-list=Block_PortScan address-list-timeout=2w chain=forward comment="NMAP FIN Stealth" protocol=tcp tcp-flags=fin,!syn,!rst,!psh,!ack,!urg
add action=add-src-to-address-list address-list=Block_PortScan address-list-timeout=2w chain=forward comment="SYN/FIN" protocol=tcp tcp-flags=fin,syn
add action=add-src-to-address-list address-list=Block_PortScan address-list-timeout=2w chain=forward comment="SYN/RST" protocol=tcp tcp-flags=syn,rst
add action=add-src-to-address-list address-list=Block_PortScan address-list-timeout=2w chain=forward comment="FIN/PSH/URG" protocol=tcp tcp-flags=fin,psh,urg,!syn,!rst,!ack
add action=add-src-to-address-list address-list=Block_PortScan address-list-timeout=2w chain=forward comment="ALL/ALL" protocol=tcp tcp-flags=fin,syn,rst,psh,ack,urg
add action=add-src-to-address-list address-list=Block_PortScan address-list-timeout=2w chain=forward comment="NMAP NULL" protocol=tcp tcp-flags=!fin,!syn,!rst,!psh,!ack,!urg
