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
