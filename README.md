# recon-auto

Interactive recon pipeline that chains Masscan, Nmap, Gobuster, and GoSpider with guided prompts. Run one script, get a full picture of the target.

## Pipeline

```
Target IP/Domain
      |
      +-- Masscan    -->  fast full TCP port scan
      +-- Nmap       -->  service/version/script scan on open ports
      +-- Gobuster   -->  directory, subdomain, and vhost enumeration
      +-- GoSpider   -->  web crawl (direct or via proxy)
```

Each stage is optional — pick what you need per run.

## Requirements

Install the following and ensure they are in `PATH`:

| Tool | Install |
|---|---|
| [Masscan](https://github.com/robertdavidgraham/masscan) | `apt install masscan` |
| [Nmap](https://nmap.org) | `apt install nmap` |
| [Gobuster](https://github.com/OJ/gobuster) | `go install github.com/OJ/gobuster/v3@latest` |
| [GoSpider](https://github.com/jaeles-project/gospider) | `go install github.com/jaeles-project/gospider@latest` |
| Python 3 | `apt install python3` |

Masscan and Nmap require `sudo`.

## Usage

```bash
git clone https://github.com/im-whoami/recon-auto
cd recon-auto
python3 reconnaissance_script.py
```

Follow the prompts:

```
Enter the target IP address: 10.10.10.10
Enter the target domain for subdomain/vhost enumeration: example.com
Run Masscan? (y/n): y
Run Nmap? (y/n): y
Run Gobuster directory scan? (y/n): y
Run Gobuster subdomain scan? (y/n): n
Run GoSpider? (y/n): y
```

## Output files

| File | Contents |
|---|---|
| `masscan_output.txt` | Open ports |
| `nmap_scan.*` | Service/version details (multiple formats) |
| `gobuster_scan.txt` | Discovered directories |
| `gobuster_subdomains.txt` | Subdomains |
| `gobuster_vsubdomains.txt` | Virtual hosts |

## Notes

- Masscan is aggressive — tune the rate limit for your environment
- Ensure wordlists are present and paths in the script match your system
- Only run against targets you have explicit authorization to test

## License

MIT

## Disclaimer

Unauthorized scanning is illegal. Use only on systems you own or have written permission to test.
