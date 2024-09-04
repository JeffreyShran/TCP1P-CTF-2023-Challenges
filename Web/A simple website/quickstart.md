# AppSec October 2024 CTF Quickstart Notes
> This should ony take 15-25 minutes depending on experience and internet speed etc etc
## How to set up Hyper-V with Kali
- See this for step-by-step instructions on how to install Hyper-V: https://techcommunity.microsoft.com/t5/educator-developer-blog/step-by-step-enabling-hyper-v-for-use-on-windows-11/ba-p/3745905
- See this for how to get started with Kali on Hyper-V: https://www.kali.org/docs/virtualization/import-premade-hyperv/

This is the correct virtual machine image to download if you're unsure:
![This is the correct image to download](https://github.com/JeffreyShran/TCP1P-CTF-2023-Challenges/blob/c58d5579e79c02e4857d5dcbafbd8a4c38fed005/Web/A%20simple%20website/hyper.png)


## How to install docker.io and docker-compose on Kali
> Run the following as a single command (`Shift + Insert`, to paste into the terminal)
- `sudo apt-get update && sudo apt-get install docker.io docker-compose -y && sudo systemctl enable docker --now && docker --version`

 ## How to clone and run challenge
> Run the following as a single command (`Shift + Insert`, to paste into the terminal)
- `git init appsec-ctf-demo && cd appsec-ctf-demo && git remote add origin https://github.com/JeffreyShran/TCP1P-CTF-2023-Challenges.git && git config core.sparseCheckout true && echo "Web/A simple website" >> .git/info/sparse-checkout && git pull --depth=1 origin main && cd "Web/A simple website/" && sudo docker-compose up`
> For info, the `docker-compose up` part takes a while, this is normal.
- Now visit [http://localhost:45681](http://localhost:45681/) to access the web challenge.

## Basic web application testing procedure
If you have no idea where to start, this might help.

1. **Reconnaissance**
   - **Passive Recon:** Not relevant for CTF, but more generally we might gather information without interacting directly (e.g., WHOIS, DNS records, public data).
   - **Active Recon:** Interact with the target to gather more detailed information (e.g., port scanning, service enumeration, technology discovery, manual exploration).

2. **Exploitation**
   - **Identify Vulnerabilities:** Use tools and manual investigation to detect direct or indirect (3rd party) vulnerabilities.
   - **Use exploits:** Use exploits to build an attack chain, usually with the aim to gain access to the target, escalate privileges, or exfiltrate data.

3. **Post-Exploitation** *Not (usually) relevant for CTF in the traditional sense. But I documented it as it can be an important step.*
   - **Persistence**
   - **Data Exfiltration**

5. **Reporting** *Not (usually) relevant for CTF in the traditional sense. But I documented it as it can be an important step.*
   - **Document Findings:** Create a report of vulnerabilities, exploits, and provide guidance on how to fix the issues discovered. *(For capture the flag, we will simply extract and report the flag)*
