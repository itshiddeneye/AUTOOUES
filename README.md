# AUTOOUES
AUTOOUES is a powerful and fully automated Bash script for identifying subdomain takeover vulnerabilities. It simplifies the workflow by
## Features ![AUTOOUES](https://github.com/user-attachments/assets/3cb7e0fe-4ded-4880-9adf-d6e09eae4c67)

1. Automated Subdomain Enumeration: Discovers subdomains using subfinder.
2. Intelligent CNAME Analysis: Identifies CNAME records pointing to external services and checks if those services are unresolved or potentially available for registration (via dig and whois).
3. Targeted Nuclei Scanning: Automatically feeds potentially vulnerable CNAME targets to nuclei using specific subdomain takeover templates for precise validation.
4. Organized Output: Creates a dedicated directory for each scan, saving all results (discovered subdomains, CNAME analysis, Nuclei findings) within it.
5. Interactive Menu: Provides an easy-to-use menu for initiating scans
6. Credit: Includes a credit line for the tool's creator.
