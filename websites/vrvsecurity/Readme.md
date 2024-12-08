# VRV Security Vulnerability Analysis

This README outlines the step-by-step approach used to analyze the security vulnerabilities of the `vrvsecurity.in` website and the tools utilized in the process. Additionally, it highlights the findings and the direction for developing custom tools to enhance security research.

## Workflow

1. **Access and Preliminary Checks**
   - Initially accessed the `vrvsecurity.in` website.
   - Verified potential exposure of the frontend roles.

2. **VirusTotal Scan**
   - Conducted a comprehensive security analysis using [VirusTotal](https://www.virustotal.com/).
   - Examined the domain for malicious behavior or flagged vulnerabilities.
    ![image](https://github.com/user-attachments/assets/73511ba7-7b93-4604-8501-3e805d8be2ab)

3. **Ping Operation**
   - Pinged the domain `vrvsecurity.in` to gather basic network information and test its reachability.
   - Recorded the IPv4 address for further exploration.
  ![image](https://github.com/user-attachments/assets/3dcacdfd-6385-4ed6-80e5-40710d7d1e72)

4. **Port Scanning**
   - Used `nmap` to perform an in-depth scan of the identified IP address.
   - Command executed: `nmap -p- -sV <IPv4 Address>`
   - Results revealed the following open ports:
     - **22/tcp**: OpenSSH 9.6p1 (Ubuntu)
     - **80/tcp**: HTTP running on nginx 1.24.0
     - **443/tcp**: SSL/HTTP running on nginx 1.24.0
  ![image](https://github.com/user-attachments/assets/02b8da68-2233-4bd8-a7d3-f3bae498a414)

5. **Findings and Insights**
   - The website’s backend services exposed critical ports, including SSH and HTTP/HTTPS.
   - Identified potential areas for exploitation such as outdated software versions or insecure configurations.
  ![image](https://github.com/user-attachments/assets/156b77b0-5d18-4a59-b4a1-a58d15b89e81)

## Next Steps

- **Tool Development**
  - Start building custom tools for:
    - Automated vulnerability scanning
    - Secure API endpoint testing
    - Real-time monitoring of exposed ports
  - Focus on integrating these tools with existing platforms for seamless usage.

- **Advanced Analysis**
  - Research deeper into potential exploits using identified open ports.
  - Explore other subdomains or associated assets for a more comprehensive assessment.

## Tools and Commands Used

- **VirusTotal**: Online domain scanning.
- **Ping**: Basic network reachability check.
  ```bash
  ping vrvsecurity.in
  ```
- **Nmap**: Port scanning and service version detection.
  ```bash
  nmap -p- -sV <IPv4 Address>
  ```
# the scam website decision 
this is scam website concluded through https://vrvsecurity.in/#privacy-policy https://vrvsecurity.in/#terms-of-service https://vrvsecurity.in/#cookies-settings
