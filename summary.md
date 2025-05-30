# **Firewall Traffic Filtering – Summary**

A firewall is a security system that monitors and controls incoming and outgoing network traffic based on predefined rules. It acts like a gatekeeper, allowing or blocking traffic to protect a computer or network.

1. Traffic Direction

- Inbound traffic: Data coming into the system (e.g., from the internet to your device).
- Outbound traffic: Data going out from your system to other devices or the internet.

2. Rule-Based Filtering
   
Firewalls use a list of rules to decide what to do with each packet of data. Rules can filter based on:

- Protocol (e.g., TCP, UDP)
- Source or destination IP addresses
- Source or destination port numbers
- Direction of traffic
- Action to take:
  -ACCEPT – Allow the traffic
  -DROP – Silently block the traffic
  -REJECT – Block the traffic and send an error message

3. Chains and Policies (for tools like iptables or nftables)
   
-Traffic is processed through predefined chains:
   -INPUT – For traffic coming into the system
   -OUTPUT – For traffic going out of the system
   -FORWARD – For traffic passing through (used on routers)

-Each chain can have a default policy (e.g., ACCEPT or DROP) that applies if no rules match.

4. Types of Firewalls

-Host-based firewalls: Run on individual devices to protect them (e.g., iptables, ufw).

-Network-based firewalls: Protect entire networks from outside threats.

5. Stateful vs Stateless

-Stateful firewalls: Keep track of ongoing connections and allow related traffic.

-Stateless firewalls: Evaluate each packet on its own, without context.

## Purpose
Firewalls are designed to allow trusted, expected traffic and block harmful, unauthorized traffic to keep systems and networks secure.

