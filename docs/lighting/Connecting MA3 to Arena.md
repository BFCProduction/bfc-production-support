It is possible to control the LED wall from the lighting console. In order to do that the MA3 console needs to output Art-Net and Resolume Arena needs to be able to receive Art-Net. 


Prior to connecting the MA3 to Arena:

- The MA3 console needs to be connected to the lighting VLAN (.70) 
- The Arena computer needs to be connected to the lighting VLAN (.70) and the network interface connected to the lighting VLAN needs to be first in the service order. 
- Confirm that the MA3 can control lights 
- Confirm that Arena can control the LED wall on it's own.

!!!!! *We have found that it is nessecary to make all network interfaces on the Arena computer inactive in order to get Arena to initially see the Art-Net signal. Once Arena is connected you can go back and make those other network interfaces active. This is necessary to send and receive video via NDI on the Video VLAN (.60) and send and receive audio via DANTE on the Dante VLAN (.51)*
## GrandMA 3 Setup

navigate to Settings>Network Protocols > Art Net

![[Screenshot 2026-03-09 at 3.23.51 PM.png]]

#### MA3 settings

**Enabled:** *Yes*
**Mode:** *Broadcast*
**Destination IP:** *blank*
**Local Universe:** *10*
**Amount:** *1*
**Net:** *0*
**Art-Net Sub-Net:** *0*
**Universe:** *10*
**Art-Net Absolute:** *10*


## Arena Setup

- Navigate to arena > preferences > DMX 
- Make sure the correct network adapter is selected. 
- Monitor set to Subnet 0 and Universe 10. 

Once you see DMX you can enable the other NIC's again


