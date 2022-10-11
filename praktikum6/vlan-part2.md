# VLAN menggunakan 3 Switch dan 1 Router

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/brszlo6wtgomall1y6o0.png)

## Switch 1
```
Switch>en
Switch>enable
Switch#conf t
Switch(config)#vlan 50
Switch(config-vlan)#name dewi
Switch(config-vlan)#exit
Switch(config)#vlan 60
Switch(config-vlan)#name wulandari
Switch(config-vlan)#exit
Switch(config)#int fa0/1
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 50
Switch(config-if)#exit
Switch(config)#int fa0/2
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 50
Switch(config-if)#exit

Switch#conf t
Switch(config)#int fa0/3
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 60
Switch(config-if)#exit
Switch(config)#int fa0/4
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 60
Switch(config-if)#exit
Switch(config)#
Switch(config)#int fa0/5
Switch(config-if)#switchport mode trunk
Switch(config-f)#exit
```
## Switch 2
```
Press RETURN to get started.

Switch>en
Switch>enable
Switch#conf t
Enter configuration commands, one per line. End with CNTL/Z.
Switch(config)#vlan 50
Switch(config-vlan)#name dewi
Switch(config-vlan)#exit
Switch(config)#vlan 60
Switch(config-vlan)#name wulandari
Switch(config-vlan)#exit
Switch(config)#int fa0/1
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 50
Switch(config-if)#exit
Switch(config)#int fa0/2
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 50
Switch(config-if)#exit
Switch(config)#int fa0/3
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 60
Switch(config-if)#ex
Switch(config)#int fa0/4
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 60
Switch(config-if)#exit
Switch(config)#
Switch>en
Switch>enable
Switch#conf t
Switch(config)#intgigabitEthernet 0/5
Switch(config-if)#switchport mode trunk
Switch(config-if)#
```

## Switch 3
```bash
Switch>en
Switch>enable
Switch#conf t
Switch(config)#vlan 50
Switch(config-vlan)#name dewi
Switch(config-vlan)#exit
Switch(config)#vlan 60
Switch(config-vlan)#name wulandari
Switch(config-vlan)#exit
Switch(config)#int fa0/1
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 50
Switch(config-if)#exit
Switch(config)#int fa0/2
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 50
Switch(config-if)#exit

Switch#conf t
Switch(config)#int fa0/3
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 60
Switch(config-if)#exit
Switch(config)#int fa0/4
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan 60
Switch(config-if)#exit
Switch(config)#
Switch(config)#int fa0/5
Switch(config-if)#switchport mode trunk
Switch(config-f)#exit
```

## ROUTER 1
```
 --- System Configuration Dialog ---

Continue with configuration dialog? [yes/no]: n


Press RETURN to get started!

Router>en
Router>enable
Router#conf t
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#int gig
Router(config)#intgigabitEthernet 0/0
Router(config-if)#ip add 192.168.10.5 255.255.255.252
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#exit
Router(config)#int gig
Router(config)#intgigabitEthernet 0/0
Router(config-if)#ip add 192.168.20.1 255.255.255.0
Router(config-if)#no shut
Router(config-if)#exit
Router(config)#int gig
Router(config)#intgigabitEthernet 0/0.50
Router(config-subif)#encapsulation dot1Q 50
Router(config-subif)#ip add 192.168.50.135 255.255.255.128
Router(config-subif)#exit
Router(config)#intgigabitEthernet 0/0.60
Router(config-subif)#
Router(config-subif)#encapsulation dot1Q 60
Router(config-subif)#ip add 192.168.60.71 255.255.255.192
Router(config-subif)#exit
Router(config)#
```

