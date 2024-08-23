# AppSec October 2024 CTF Quickstart Notes
## How to set up Hyper-V with Kali
- See: https://www.kali.org/docs/virtualization/import-premade-hyperv/

## How to install docker.io and docker-compose on Kali
- `sudo apt-get update && sudo apt-get install docker.io docker-compose -y && sudo systemctl enable docker --now && docker --version`

 ## How to clone and run challenge
 The `docker-compose up` part takes a while, this is normal.
- `git init appsec-ctf-demo && cd appsec-ctf-demo && git remote add origin https://github.com/JeffreyShran/TCP1P-CTF-2023-Challenges.git && git config core.sparseCheckout true && echo "Web/A simple website" >> .git/info/sparse-checkout && git pull --depth=1 origin main && cd "Web/A simple website/" && sudo docker-compose up`
- Now visit [http://localhost:45681](http://localhost:45681/) to access the web challenge.

## Basic web application testing procedure
If you have no idea where to start, this might help.

1. **Reconnaissance**
   - **Passive Recon:** Not relevant for CTF, but more generally we might gather information without interacting directly (e.g., WHOIS, DNS records, public data).
   - **Active Recon:** Interact with the target to gather more detailed information (e.g., port scanning, service enumeration, technology discovery, manual exploration).

2. **Exploitation**
   - **Identify Vulnerabilities:** Use tools and manual investigation to detect direct or indirect (3rd party) vulnerabilities.
   - **Use exploits:** Use exploits to build an attack chain, usually with the aim to gain access to the target, escalate privileges, or exfiltrate data.

3. **Post-Exploitation**
   - **Maintain Access:** Not relevant for CTF, but more generally we set up backdoors or other methods to retain access.
   - **Data Extraction:** Not (usually) relevant for CTF, but more generally we extract sensitive information if needed.

4. **Reporting**
   - **Document Findings:** Create a report of vulnerabilities, exploits, and provide guidance on how to fix the issues discovered. *(For capture the flag, we will simply extract and report the flag)*
