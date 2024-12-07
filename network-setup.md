# Task 2 
## List of devices used in this network

1. ***Router***
   - Quantity: 1
   - Model: Cisco 1941
   - IP: 168.90.0.1 (for GigabitEthernet 0/0)
   - IP: 210.3.14.1 (for GigabitEthernet 0/1) 
2. ***Switches***
   - Quantity: 2
   - Model: 2960-24TT
3. ***PCs***
   - Quantity: 5
   - Model: PC-PT (generic pc)
   - IP (PC0): 168.90.0.2
   - IP (PC1): 168.90.0.3
   - IP (PC2): 210.3.14.2
   - IP (PC3): (dodijeljena adresa preko dhcp 168.90.0.6)
   - IP (PC4): (dodijeljena adresa preko dhcp 210.3.14.5)
4. ***Laptop***
   - Quantity: 1
   - Model: Laptop-PT
   - IP: 168.90.0.4
5. ***Servers***
   - Quantity: 3
   - Model: Server-PT
   - IP (Server0): 168.90.0.5 (on Switch1)
   - IP (Server1): 210.3.14.3 (on Switch2)
   - IP (Server2): 210.3.14.4 (on Switch2)

[Link to my github repository](https://github.com/nejlahasanovic/IBU062_Assignment3_NejlaHasanovic.git)

## DHCP commands
1. **DHCP commands and steps i used for configuration**
   
   ```bash
   ip dhcp pool MYPOOL1 "I created a DHCP pool named MYPOOL1. This pool is responsible for assigning IP addresses to devices connected to the first network (168.90.0.0/16)"
   network 168.90.0.0 255.255.0.0 "I specified the network range for MYPOOL1. Devices on this network will receive IP addresses from the 168.90.0.0/16 range"
   default-router 168.90.0.1 "I set the default gateway for this network to 168.90.0.1. Devices will use this IP address to communicate with other networks."
   exit "After completing the configuration for MYPOOL1, I exited the pool setup."
   
   
   ip dhcp pool MYPOOL2 "I created a second DHCP pool named MYPOOL2. This pool assigns IP addresses to devices connected to the second network (210.3.14.0/24)."
   network 210.3.14.0 255.255.255.0 "I defined the network range for MYPOOL2. Devices on this network will receive IP addresses from the 210.3.14.0/24 range."
   default-router 210.3.14.1 "I set the default gateway for the second network to 210.3.14.1, enabling devices to communicate outside their local network."
   exit "I exited the setup after completing the configuration for MYPOOL2."