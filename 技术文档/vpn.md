luna@bogon  /etc/ppp  sudo route -n add -net 192.168.1.0/24 192.168.3.1
route: writing to routing socket: File exists
add net 192.168.1.0: gateway 192.168.3.1: File exists
 luna@bogon  /etc/ppp  sudo route delete 192.168.1.0
delete net 192.168.1.0
 luna@bogon  /etc/ppp  sudo route -n add -net 192.168.1.0/24 192.168.3.1
add net 192.168.1.0: gateway 192.168.3.1