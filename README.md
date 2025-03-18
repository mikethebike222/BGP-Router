Overview

This project implements a simplified BGP router that manages route announcements, revocations, and data packet forwarding within a simulated network.  
The router adheres to BGP protocol rules, including route aggregation, relationship-based forwarding, and longest prefix matching.  
Key Features Include,   
  
Multi-Socket Management:  
    - Uses select() to handle multiple UDP sockets for simultaneous communication with neighboring routers.  
       
Route Management:  
    - Processes update and withdraw messages to maintain a forwarding table.    
    - Aggregates adjacent subnets with matching attributes to compress the table.  
    - Disaggregates routes when withdrawals occur, rebuilding the table from stored updates.  
        
Data Forwarding:  
    - Applies longest prefix matching and tie-breaking rules (local preference, AS path length, origin type) to select optimal routes.  
    - Enforces provider/customer/peer relationships to determine legal forwarding.   
         
Simulator Integration:   
    - Compatible with provided test cases to validate correctness and performance.    

Installation:  
After you clone the repository make sure to give the files 'run', 'BGProuter', and 'test' the executable permission.  
There are no external libraries so to run a test command just use the run scripting command to do a single test case as seen below,  

./run configs/1-1-simple-send.conf  

In order to run all test commands use,   
./test
