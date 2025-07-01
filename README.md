< align="center"> ![AUTOOUES](https://github.com/user-attachments/assets/3cb7e0fe-4ded-4880-9adf-d6e09eae4c67) >

## 📝 Description

**AUTOOUES** is a powerful and automated Bash script designed to identify potential subdomain takeover vulnerabilities. It streamlines the process by first enumerating all subdomains for a given target, then performing intelligent CNAME record checks, and finally leveraging the `nuclei` tool with specialized templates for deeper validation on potentially vulnerable targets. All scan results are neatly organized into a dedicated directory named after the target domain.

## ✨ Features

* **Automated Subdomain Enumeration:** Discovers subdomains using `subfinder`.

* **Intelligent CNAME Analysis:** Identifies CNAME records pointing to external services and checks if those services are unresolved or potentially available for registration (via `dig` and `whois`).

* **Targeted Nuclei Scanning:** Automatically feeds potentially vulnerable CNAME targets to `nuclei` using specific subdomain takeover templates for precise validation.

* **Organized Output:** Creates a dedicated directory for each scan, saving all results (discovered subdomains, CNAME analysis, Nuclei findings) within it.

* **Interactive Menu:** Provides an easy-to-use menu for initiating scans.


## 🛠️ Prerequisites

Before running `AUTOOUES`, ensure you have the following tools installed on your system. These are common tools in penetration testing environments like Kali Linux, but can be installed on most Linux distributions and macOS.

1.  **`subfinder`**: For passive subdomain enumeration.

    * **Installation:** Follow instructions on [ProjectDiscovery/subfinder GitHub](https://github.com/projectdiscovery/subfinder).

        ```bash
        # If you have Go installed (recommended method)
        go install -v [github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest](https://github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest)
        ```

        Ensure `~/go/bin` is in your PATH.

2.  **`dig`**: For DNS lookups (part of `dnsutils` or `bind-utils`).

    * **Installation (Debian/Ubuntu):**

        ```bash
        sudo apt update
        sudo apt install dnsutils
        ```

    * **Installation (CentOS/RHEL):**

        ```bash
        sudo yum install bind-utils
        ```

    * **Installation (macOS with Homebrew):**

        ```bash
        brew install dnsutils
        ```

3.  **`whois`**: For querying WHOIS information.

    * **Installation (Debian/Ubuntu):**

        ```bash
        sudo apt update
        sudo apt install whois
        ```

    * **Installation (CentOS/RHEL):**

        ```bash
        sudo yum install whois
        ```

    * **Installation (macOS with Homebrew):**

        ```bash
        brew install whois
        ```

4.  **`nuclei`**: For vulnerability scanning with templates.

    * **Installation:** Follow instructions on [ProjectDiscovery/nuclei GitHub](https://github.com/projectdiscovery/nuclei).

        ```bash
        # If you have Go installed (recommended method)
        go install -v [github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest](https://github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest)
        ```

        Ensure `~/go/bin` is in your PATH.

    * **Update Nuclei Templates (Crucial!):** After installing `nuclei`, always run this command to get the latest templates:

        **Copy and paste this command into your terminal:**
        ```bash
        nuclei -update-templates
        ```

## 🚀 Installation

1.  **Clone the repository (once uploaded to GitHub) or download the script:**

    ```bash
    git clone [https://github.com/your-username/AUTOOUES.git](https://github.com/your-username/AUTOOUES.git)
    cd AUTOOUES
    ```

    *(For now, you'll just copy the script content into a file.)*

2.  **Make the script executable:**

    ```bash
    chmod +x auto_takeover_scanner.sh
    ```

## 💻 Usage

### Interactive Mode (Recommended)

Run the script without any arguments to enter the interactive menu:

```bash
./auto_takeover_scanner.sh
```

You will be greeted with the tool's banner and a menu:

```
  █████╗ ██╗   ██╗████████╗ ██████╗  ██████╗ ██╗   ██╗███████╗███████╗
 ██╔══██╗██║   ██║╚══██╔══╝██╔═══██╗██╔═══██╗██║   ██║██╔════╝██╔════╝
 ███████║██║   ██║   ██║   ██║   ██║██║   ██║██║   ██║█████╗  ███████╗
 ██╔══██║██║   ██║   ██║   ██║   ██║██║   ██║██║   ██║██╔══╝  ╚════██║
 ██║  ██║╚██████╔╝   ██║   ╚██████╔╝╚██████╔╝╚██████╔╝███████╗███████║
 ╚═╝  ╚═╝ ╚═════╝    ╚═╝    ╚═════╝  ╚═════╝  ╚═════╝ ╚══════╝╚══════╝
           Automated Subdomain Takeover Scanner
           --------------------------------------
           Made by @ethical_kunal (Kunal Kumar)

Main Menu:
1. Scan a new domain
2. Exit

Enter your choice (1 or 2):
```

Choose option `1` and follow the prompts to enter your target domain.

### Direct Scan Mode

You can also provide the target domain directly as a command-line argument for a one-time scan:

```bash
./auto_takeover_scanner.sh example.com
```

*(Replace `example.com` with your actual target domain.)*

### Output

For each scan, a new directory will be created in the format `yourdomain_com_scan_results` (e.g., `example_com_scan_results/`). This directory will contain the following files:

* `yourdomain_com_discovered_subdomains.txt`: A list of all subdomains found by `subfinder`.

* `yourdomain_com_cname_takeover_results.txt`: Detailed output of the CNAME checks, including potential takeover flags and WHOIS information.

* `yourdomain_com_potential_takeover_targets.txt`: A temporary file listing only the CNAME targets identified as potentially vulnerable, used as input for Nuclei.

* `yourdomain_com_nuclei_takeover_results.txt`: The results from the `nuclei` scan, indicating confirmed subdomain takeover vulnerabilities.

## 🤝 Credits

This tool was created by:

**@ethical_kunal (Kunal Kumar)**

## 💡 Contributing

Contributions are welcome! If you have suggestions for improvements, new features, or bug fixes, please feel free to:

1.  Fork the repository.

2.  Create a new branch (`git checkout -b feature/YourFeature`).

3.  Make your changes.

4.  Commit your changes (`git commit -m 'Add some feature'`).

5.  Push to the branch (`git push origin feature/YourFeature`).

6.  Open a Pull Request.

## 📄 License

This project is open-source and available under the [MIT License](https://opensource.org/licenses/MIT).

## 🚀 How to Upload this Tool to GitHub

Follow these steps to upload your `auto_takeover_scanner.sh` script and its `README.md` to a new GitHub repository.

**Step 1: Create a New Repository on GitHub**

1.  Go to [GitHub](https://github.com/) and log in to your account.

2.  On the left sidebar, click on the **"New"** button (or the `+` sign in the top right corner and select "New repository").

3.  **Repository name:** Enter `AUTOOUES` (or any name you prefer for your tool).

4.  **Description (Optional):** Add a short description, e.g., "Automated Subdomain Takeover Scanner".

5.  **Public/Private:** Choose `Public` if you want others to see and use your tool, or `Private` if you want to keep it to yourself for now.

6.  **Initialize this repository with:**

    * **DO NOT** check "Add a README file" (we're creating our own).

    * **DO NOT** check "Add .gitignore".

    * **DO NOT** check "Choose a license" (we'll add it manually, or you can add it here if you prefer).

7.  Click the **"Create repository"** button.

**Step 2: Initialize a Local Git Repository**

1.  **Open your terminal** on your local machine.

2.  **Navigate to the directory** where your `auto_takeover_scanner.sh` script is located.

    ```bash
    cd /path/to/your/script/directory
    ```

3.  **Create the `README.md` file:** Copy the content of this immersive into a new file named `README.md` in the same directory as your script.

    ```bash
    # You can use a text editor:
    nano README.md
    # Paste the content, then save and exit (Ctrl+X, Y, Enter for nano)
    ```

4.  **Initialize a new Git repository** in your current directory:

    ```bash
    git init
    ```

**Step 3: Add and Commit Your Files**

1.  **Add your script and README file** to the staging area:

    ```bash
    git add auto_takeover_scanner.sh README.md
    ```

    *(If you have other files you want to include, add them here too, e.g., `git add .` to add all files in the current directory.)*

2.  **Commit your changes:**

    ```bash
    git commit -m "Initial commit of AUTOOUES scanner"
    ```

**Step 4: Connect to GitHub and Push**

1.  **Go back to your GitHub repository page** (the one you just created). You should see instructions under "Quick setup".

2.  **Copy the remote repository URL.** It will look something like: `https://github.com/your-username/AUTOOUES.git`

3.  **Add the remote origin** to your local repository:

    ```bash
    git remote add origin [https://github.com/your-username/AUTOOUES.git](https://github.com/your-username/AUTOOUES.git)
    ```

    *(Replace the URL with the one you copied from your GitHub page.)*

4.  **Push your local commits to GitHub:**

    ```bash
    git push -u origin main
    ```

    *(GitHub recently changed the default branch name from `master` to `main`. If `main` doesn't work, try `git push -u origin master`.)*

5.  **Enter your GitHub username and Personal Access Token (PAT)** when prompted.

    * **Note:** GitHub no longer accepts passwords for Git operations. You need to create a Personal Access Token (PAT).

    * **How to create a PAT:**

        1.  Go to GitHub.com.

        2.  Click your profile picture (top right) -> `Settings`.

        3.  Scroll down to `Developer settings` (left sidebar).

        4.  Click `Personal access tokens` -> `Tokens (classic)`.

        5.  Click `Generate new token` -> `Generate new token (classic)`.

        6.  Give it a descriptive name (e.g., "Git CLI Token").

        7.  Set an expiration date.

        8.  Under "Select scopes," check `repo` (full control of private repositories) and other scopes as needed.

        9.  Click `Generate token`.

        10. **IMPORTANT:** Copy the generated token immediately! You won't be able to see it again. Use this token as your password when prompted by `git push`.

**Step 5: Verify on GitHub**

1.  Refresh your GitHub repository page. You should now see your `auto_takeover_scanner.sh` script and `README.md` file listed there!

Congratulations! Your `AUTOOUES` tool is now live on GitHub.
