# Aruba-6100-Switch-Installation-Guide


screen /dev/tty "porta q ta conectado" "velocidade"

INSTALL GNU SCREEN ON LINUX DISTRO
DMESG = to localize switch

#***************************************************************************************************
# SW-ARUBA-6100-XX
#***************************************************************************************************
conf

hostname SW-ARUBA-6100-X
interface vlan 1
ip address 172.21.39.6X/22
no ip dhcp



#***************************************************************************************************
# SNMP-SERVER
#***************************************************************************************************
snmp-server vrf default
snmp-server community secel
snmp-server system-contact Equipe de Redes - SECEL-MT
snmp-server system-location Datacenter - SECEL-MT
snmp-server system-description Switch Aruba 6100 48p

wr mem
