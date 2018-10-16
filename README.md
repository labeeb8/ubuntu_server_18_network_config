# ubuntu_server_18_network_config

sudo lshw -C network

ifconfig

ip link

sudo ip link set enp1s0 up

sudo nano /etc/netplan/50-cloud-init.yaml


network:
  ethernets:
    enp1s0:
      addresses: []
      dhcp4: true
  version: 2
  wifis:
    wlp2s0:
      access-points:
        "WesternDigital-0b":
          password: "WireLess2.4GHz"
      dhcp4: true
      dhcp6: no



example wireless config
cat /usr/share/doc/netplan.io/examples/wireless.yaml




sudo netplan try
or better 
sudo netplan --debug generate

sudo netplan apply

sudo netplan ip leases enp0s3

networkctl

to troubleshoot
dmesg | grep -e wlp -e net
cat /var/log/syslog | grep -i net

check if wpasupplicant is installed:
sudo dpkg -s wpasupplicant

sudo apt install wpasupplicant

