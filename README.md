# Setup and Use a Firewall on Windows/Linux (Task - 4)

Configure and test basic firewall rules to allow or block traffic on a Windows or Linux system using native firewall tools.

---

## Tools & Environment

- **Tools Used:**
  - **Windows:** Windows Defender Firewall
  - **Linux:** UFW (Uncomplicated Firewall)
---

## Steps Performed

### For Linux Machine
---

1. To open firewall tools on Kali Linux
   ```bash
   sudo ufw status
   ```
   
   This will inform about UFW(uncomplicated Firewall) status.
   If not enabled ,it can be enabled by:
   
   ```bash
   sudo ufw enable
   ```

---
2. To list current firewall rules running on kali linux
   
   ```bash
   sudo ufw status verbose
   ```
   or
   ```bash
   sudo ufw status numbered
   ```
---

3. To add a rule to block inbounf traffic on specific port

   ```bash
   sudo ufw deny 4444/tcp
   ```
---

4. To test the rule by attempting to connect to port locally/remotely
   
   - Run a test listener (on machine with firewall)
    ```bash
    nc -lvp 4444
    ```
   - Local test (another terminal same machine)
     ```bash
     nc -vz 192.168.2.123 4444
     ```
     - Output will be in the form
     nc:listening on [any] 4444 ...192.168.2.123: inverse host lookup failed:
     Unknown host connect to [192.168.2.123] from (UNKNOWN) [192.168.2.123] 50044
   - Remote test (another machine)
     - On different machine  (same network)
       ```bash
       nc -vz 192.168.2.123 4444
       ```
---

5. To add a SSh rule
   ```bash
   sudo ufw allow ssh
   ```
   
---

6. Remove the changes to restore original state
   ```bash
   sudo ufw status numbered
   ```
   then delete using number
   ```bash
   sudo ufw delete 4
   ```
---

### For WINDOWS MACHINE
1. Open Firewall Settings:

- Go to Control Panel > System and Security > Windows Defender Firewall.
- Click on Advanced settings (left pane).

2. List Current Rules:

- In the Windows Firewall with Advanced Security window, view Inbound Rules and Outbound Rules.

3. Add a Rule to Block Inbound Traffic (e.g., port 23):

- In Inbound Rules, click New Rule…
- Choose Port, click Next.
- Select TCP or UDP (for Telnet, use TCP), and specify port 23.
- Choose Block the connection > Apply to all profiles.
- Name the rule and finish.

4. Test the Rule:

- Try connecting using a Telnet client (telnet localhost 23) or simulate a connection.

5. Allow SSH :

- Same as above, allow port 22 instead of blocking it.

6. Remove Test Block Rule:

- Right-click the rule > Delete.

---
## Outcome

- Gained practical experience configuring firewall rules.
- Understood the basics of inbound/outbound rule creation.
- Learned how to test and validate firewall behavior.
- Developed insight into how firewalls filter traffic based on port, protocol, and direction.

---

