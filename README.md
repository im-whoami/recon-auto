A powerful and interactive Python script designed to automate various reconnaissance tasks commonly performed during penetration testing and security assessments.

Features
Masscan Port Scanning:
Quickly scans all TCP ports on a target IP using Masscan with customizable rate limits. Results are saved for further analysis.

Nmap Scan:
Parses Masscan results to extract open ports, then performs an aggressive Nmap scan (-A) on those ports to gather detailed information about services and vulnerabilities.

Gobuster Directory Enumeration:
Enumerates directories and files on a target web server using a wordlist and supports multiple file extensions.

Gobuster Subdomain and Vhost Enumeration:
Performs DNS-based subdomain and virtual host enumeration for the target domain using large wordlists.

GoSpider Web Crawler:
Provides an interactive menu to run GoSpider scans either through an HTTP proxy or directly on a target site, with options for sitemap inclusion and concurrency settings.

Interactive Prompts:
User-friendly CLI prompts guide the user through selecting which scans to run and configuring scan parameters.

Prerequisites
Make sure the following tools are installed and accessible in your system’s PATH:

Masscan

Nmap

Gobuster

GoSpider

Python 3

Additionally, sudo privileges are required for Masscan and Nmap scans.

Usage
Clone or download this script.

Run the script:

bash
Copy
Edit
python3 reconnaissance_script.py
Follow the interactive prompts:

Enter the target IP address and domain.

Choose whether to run Masscan port scan.

Choose whether to run Nmap scan on discovered ports.

Choose whether to run Gobuster scans for directories, subdomains, or virtual hosts.

Choose whether to run GoSpider with proxy or site scan options.

Review the saved output files:

masscan_output.txt (Masscan results)

nmap_scan.* (Nmap results in multiple formats)

gobuster_scan.txt (Directory enumeration results)

gobuster_subdomains.txt (Subdomain enumeration results)

gobuster_vsubdomains.txt (Vhost enumeration results)

GoSpider output file as specified

Notes
Masscan can generate a large amount of traffic. Use with caution and within legal boundaries.

Ensure your wordlists are correctly installed and the file paths in the script match your system.

Running scans on targets without permission is illegal and unethical.

Adjust scan rates and concurrency in the script or via interactive prompts to suit your network environment.

Example Output
plaintext
Copy
Edit
*********************************************
            Reconnaissance Script            
*********************************************

Enter the target IP address: 192.168.1.100
Enter the target domain for Gobuster Vhost/subdomain enumeration (e.g., example.com): example.com
Do you want to use Masscan Scan? (y/n): y

Running Masscan (requires Sudo)...

[...Masscan output...]

Do you want to use Nmap scan? (y/n): y

Running Nmap scan on 192.168.1.100 for ports: 22,80,443...

[...Nmap output...]

Reconnaissance completed.
