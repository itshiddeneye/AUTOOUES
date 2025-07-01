![AUTOOUES](https://github.com/user-attachments/assets/3cb7e0fe-4ded-4880-9adf-d6e09eae4c67)
AUTOOUES is a powerful and fully automated Bash script for identifying subdomain takeover vulnerabilities. It simplifies the workflow by
## Features
- Automated Subdomain Enumeration: Discovers subdomains using > subfinder.
- Intelligent CNAME Analysis: Identifies CNAME records pointing to external services and checks if those services are unresolved or potentially available for registration (via dig and whois).
- Targeted Nuclei Scanning: Automatically feeds potentially vulnerable CNAME targets to nuclei using specific subdomain takeover templates for precise validation.
- Organized Output: Creates a dedicated directory for each scan, saving all results (discovered subdomains, CNAME analysis, Nuclei findings) within it.
- Interactive Menu: Provides an easy-to-use menu for initiating scans
- Credit: Includes a credit line for the tool's creator.
