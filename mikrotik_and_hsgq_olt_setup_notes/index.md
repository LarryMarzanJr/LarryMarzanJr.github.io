# MikroTik Routerboard and HSGQ OLT Setup Notes


# MikroTik Routerboard and HSGQ OLT Setup Notes
---

## Mikrotik Side
1. Setup DHCP Client ether1
2. Allow masquerade connection in Firewall menu
3. Create VLAN : `VLAN10-Hotspot`, `VLAN20-PPPoE`, `VLAN30-Console` under the interface
   `ether4-OLT` Create bridge `bridge-LAN` for normal DHCP ports in this case ether2 and ether3 will be the slave ports, and `bridge-hotspot` for hotspot ports in this case VLAN10 will be the
   slave port.
4. Setup IP Pool for bridge-LAN
5. Setup IP Pool for bridge-hotspot
6. Setup DHCP Server for bridge-LAN
7. Setup Hotspot Server for bridge-hotspot





---

## OLT HSGQ Side:
To setup HSGQ OLT for the first time, we power it on, then connect your Ethernet Cable from
your Laptop Ethernet Port to the HSGQ OLT `GE2` port (optionally can be plugged in to GE1,GE3,GE4 port).

Default OLT IP address is 192.168.99.1, so setup your laptop IP segment to 192.168.99.x

To access OLT, the default user is `root` and the password is `admin`. Consider changing your default root password.

> NOTE: Remember to always save your configuration in `Shortcut > Save Configuration`.

### Configure VLAN
Disable VLAN Transparent in VLAN Tab menu

Create VLAN according to the VLAN ID we've create before in MikroTik routerboard. Go to
menu `VLAN > Create`, at the pop up menu we type all the VLAN ID inside the VLAN ID textbox
separated with comma:
```
10,20,30
```
At the Tagged checklist, click Select All, so that all ports will be accessible for these
VLAN IDs we've created.

> NOTE: Remember to always save your configuration in Shortcut > Save Configuration

We can rename the VLAN as needed like ` VLAN10-Hotspot`, `VLAN20-PPPoE`, `VLAN30-Console`.

### Configure Network Interface
Now we will setup the OLT interface so that it will be accessible through MikroTik gateway.

Go to Advanced > System > Network Interface.
Click on Add Inbound Interface. At the pop-up menu input the following:
```
IP address : 10.30.1.2
IP Mask : 255.255.255.0
VLAN ID : 30
```
And then click apply.

Still in the same Network Interface menu, change the Default Route `0.0.0.0` to `10.30.1.1` And then click apply.

> NOTE: Remember to always save your configuration in Shortcut > Save Configuration

## Testing Gateway Connection
Now we can test it out by plugging in Ethernet cable from Mikrotik port at `ether4-OLT` to
HSGQ OLT port at `GE1`.

As for our Laptop, we want to move the Ethernet cable to MikroTik `ether2` or `ether3` to
test out the connectivity between HSGQ OLT and MikroTik routerboard.

