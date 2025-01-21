# 3. **Networking**
   - `ifconfig` or `ip a` – Displays network interfaces and their configurations.
   - `ping <hostname/IP>` – Checks connectivity to a remote host.
   - `netstat -tuln` – Shows active network connections and listening ports.
   - `ss -tuln` – A faster, more modern alternative to `netstat`.
   - `nmap <IP>` – Scans a target IP for open ports (you may need to install Nmap: `sudo apt install nmap`).
   - `traceroute <hostname/IP>` – Traces the route packets take to reach a target.
   - `dig <domain>` – Query DNS servers for detailed domain information.
   - `curl <URL>` – Transfer data from or to a server.