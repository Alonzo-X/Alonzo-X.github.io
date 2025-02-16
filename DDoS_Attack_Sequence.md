```mermaid
sequenceDiagram
autonumber
participant Attacker
participant BotNet
participant WebServer
participant Firewall
Attacker->>Botnet: Command to initiate attack
Botnet->>WebServer: floods requests to the server
WebServer->>Firewall: Passes through traffic
Firewall->>WebServer: Allows legit traffic through
WebServer->>Firewall: Sends overload traffic back to firwall
Note over WebServer , Firewall: Firewall blocks IP addresses of malicious bots - number 6
Firewall->>WebServer: Block malicious requests
WebServer->>BotNet: Server crashes from to much traffic
BotNet->>WebServer: Continues to flood with more requests to server
WebServer->>Firewall: WebServer has downtime from the overload
Note over WebServer , Firewall: Firewall still tries to block malicious IP addresses after overload - number 9
Create participant Alonzo
Note over Alonzo: 1 - Attacker commands the botnet to initiate the attack
Note over Alonzo: 2 - Botnet floods requests to the webserver
Note over Alonzo: 3 - Webserver passes the traffic to the firewall
Note over Alonzo: 4 - Firewall allows legitimate traffic in
Note over Alonzo: 5 - Webserver sends overload traffic back to the firewall
Note over Alonzo: 6 - Firewall blocks malicious requests
Note over Alonzo: 7 - Webserver crashes due to overload from requests
Note over Alonzo: 8 - he Botnet continues its attack by flooding the Webserver with additional requests
Note over Alonzo: 9 - The Webserver reports its downtime or overload to the firewall but the firewall continues its defense by blocking additional malicious IP addresses that belong to the Botnet
