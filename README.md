# Portspoof
(Antisyphon training lab from Cyber Deception/Active Defense)
## Portspoof
- In Kali, become root ```sudo su -```
- Install Portspoof
<pre>apt-get update</pre>
<pre>apt-get install portspoof</pre>
- Adding firewall rules:
<pre>iptables -t nat -A PREROUTING -p tcp -m tcp --dport 1:20 -j REDIRECT --to-ports 4444</pre>
- Run Portspoof
<pre>portspoof</pre>
- Use cmd to run nmap:
<pre>nmap -p 1-10 {YOUR LINUX IP}</pre>
<img width="709" alt="Screenshot 2025-03-30 at 9 43 22 PM" src="https://github.com/user-attachments/assets/019aebb1-0c80-4875-adc9-7fd8cd50abc4" /><br><br>
- A more accurate scan is the following:
<pre>nmap -p 1-10 -sV {YOUR LINUX IP}</pre>
<img width="747" alt="Screenshot 2025-03-30 at 9 51 07 PM" src="https://github.com/user-attachments/assets/15e67a22-5c05-4920-aaef-9b21d0067bf3" /><br><br>
- Let's mess with the attacker even more by getting Portspoof to fool nmap into detecting real services running
<pre>portspoof -s /etc/portspoof/portspoof_signatures</pre>
<img width="717" alt="Screenshot 2025-03-30 at 9 57 09 PM" src="https://github.com/user-attachments/assets/9aee84bb-25a0-4a89-9e98-a3eecefe9e5c" /><br><br>
- You can flush all rules with this command:
<pre>sudo iptables -t nat -F</pre>
