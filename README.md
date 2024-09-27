# Mininet with BGP Routing

## Overview

This Mininet topology simulates a network environment with autonomous systems (AS) and routers. The topology includes four autonomous systems (AS1, AS2, AS3, and AS4) and four routers (R1, R2, R3, and R4). Each router is connected to three hosts. The main objective is to demonstrate a scenario where an attacker's network (AS4) pretends to be AS3 and captures packets from AS1.

## Requirements

- Mininet (version X.XX or later)
- Python (version 3.XX or later)

## Instructions


1. Run the BGP configuration script to set up the topology:

   ```bash
   sudo python bgp.py
   ```

   This script initializes the Mininet environment with the specified topology, ASs, routers, and hosts.

2. Start the Mininet CLI:

   ```bash
   sudo mn -x
   ```


3. To simulate the attacker's network, run the rogue script on AS4:

   ```bash
   sh start_rogue.sh
   ```

   The rogue script will change the path in such a way that AS1 will be fooled into considering AS4 as the shortest path.

4. To stop the rogue script and revert to the original path, run:

   ```bash
   sh stop_rogue.sh
   ```

   This will stop the rogue script and restore the original path.

5. To exit the Mininet environment, type `exit` in the Mininet CLI.

## Files

- `bgp.py`: Mininet script for setting up the customized topology.
- `bgp.sh`: BGP routing script to initiate routing in the network.
- `start_rogue.sh`: Script to start the rogue attacker in AS4.
- `stop_rogue.sh`: Script to stop the rogue attacker and revert to the original path.

## Notes

- Ensure that customized GUI Mininet is imported in VirtualBox on your system  before running the scripts.
