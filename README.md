# Portspoof
(Antisyphon training lab from Cyber Deception/Active Defense)<br><br>
Full lab explanation available on my <a href="https://medium.com/@swathitadepalli/active-defense-and-cyber-deception-antisyphon-training-44c0ee851be4#82d9">Medium</a>
## Portspoof
- Become root in Kali: ```sudo su -```
- Install Portspoof
<pre>apt-get update</pre>
<pre>apt-get install portspoof</pre>
- Adding firewall rules:
<pre>iptables -t nat -A PREROUTING -p tcp -m tcp --dport 1:20 -j REDIRECT --to-ports 4444</pre>
- Run Portspoof
<pre>portspoof</pre>
## nmap
- Use cmd to run nmap:
<pre>nmap -p 1-10 {YOUR LINUX IP}</pre>
<img width="709" alt="Screenshot 2025-03-30 at 9 43 22 PM" src="https://github.com/user-attachments/assets/019aebb1-0c80-4875-adc9-7fd8cd50abc4" /><br><br>
- A more accurate scan would be:
<pre>nmap -p 1-10 -sV {YOUR LINUX IP}</pre>
<img width="747" alt="Screenshot 2025-03-30 at 9 51 07 PM" src="https://github.com/user-attachments/assets/15e67a22-5c05-4920-aaef-9b21d0067bf3" /><br><br>
## Spoofing Services
- Let’s mess with the attacker by getting Portspoof to fool nmap into detecting real services running:
<pre>portspoof -s /etc/portspoof/portspoof_signatures</pre>
<pre>nmap -p 1-10 -sV {YOUR LINUX IP}</pre>
<img width="717" alt="Screenshot 2025-03-30 at 9 57 09 PM" src="https://github.com/user-attachments/assets/9aee84bb-25a0-4a89-9e98-a3eecefe9e5c" /><br><br>
- For reference, a normal scan without Portspoof running:
<img width="755" alt="Screenshot 2025-03-30 at 10 06 38 PM" src="https://github.com/user-attachments/assets/388fe4b5-d307-4fd6-a5a9-452cb2e6f377" /><br><br>

- You can flush all rules with this command:
<pre>sudo iptables -t nat -F</pre><br><br>
<a href="https://github.com/swathinator/Homelabs">Back to Homelabs</a>
