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
   - - Output will be in the form
     nc:listening on [any] 4444 ...192.168.2.123: inverse host lookup failed:
     Unknown host connect to [192.168.2.123] from (UNKNOWN) [192.168.2.123] 50044
   - Remote test (another machine)
   - - On different machine  (same network)
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
   sudo ufw delete <number>
   ```
---
## Outcome

- Gained practical experience configuring firewall rules.
- Understood the basics of inbound/outbound rule creation.
- Learned how to test and validate firewall behavior.
- Developed insight into how firewalls filter traffic based on port, protocol, and direction.

---

