<h1>Subminer Tool</h1>

<h2>About</h2>
Subminer is a Python-based tool designed for subdomain enumeration. It allows users to search for subdomains of a given domain by leveraging web scraping techniques. The tool sends an HTTP GET request to the specified URL, extracts the response HTML, and uses regular expressions to find and display the discovered subdomains. Additionally, users have the option to save the results to a file.

<h2>Features</h2>
- Subdomain enumeration: Subminer retrieves and displays the subdomains associated with a specified domain.<br>
- Custom DNS server: Users can choose to use a custom DNS server for the subdomain lookup.<br>
- User-Agent header: The tool utilizes a User-Agent header resembling a popular web browser to increase compatibility and avoid detection.<br>
- Save results: Users have the option to save the list of discovered subdomains to a file in either txt or csv format.<br>

<h2>User Types</h2>
Subminer is suitable for:
- Penetration testers and security researchers who need to gather information about a target domain.<br>
- System administrators who want to assess their domain's security posture by identifying potential subdomains that may have been unintentionally exposed.<br>

<h2>Required Packages</h2>
Subminer requires the following packages:<br>
- argparse<br>
- socket<br>
- requests<br>
- csv<br>
- pyfiglet<br>
<h2>Installation</h2>
To install Subminer in Kali Linux, you can follow these steps:

1. Open a terminal.
2. Clone the Subminer repository from GitHub using the following command:
   <pre><code>$ git clone https://github.com/username/subminer.git</code></pre>
   Replace `username` with the actual username of the repository owner.
3. Navigate to the Subminer directory:
   <pre><code>$ cd subminer</code></pre>
4. Install the required packages using pip:
   <pre><code>$ pip install -r requirements.txt</code></pre>
5. Run Subminer using the Python command:
   <pre><code>$ python subminer.py</code></pre>

Note: Make sure you have Python and pip installed on your Kali Linux system before proceeding with the installation. Additionally, you may need to use `sudo` with the commands if you encounter any permission issues.

Example of commands in Kali Linux for installation:

```bash
$ git clone https://github.com/username/subminer.git
$ cd subminer
$ pip install -r requirements.txt
$ python subminer.py
```

In the above example, the user clones the Subminer repository from GitHub, navigates to the cloned directory, installs the required packages using pip, and finally runs the Subminer tool using the Python command.

<h2>Usage</h2>
$ cd /path/to/subminer/<br>
$ python subminer.py<br>
To use Subminer in Kali Linux, follow these steps:
1. Open a terminal.<br>
2. Navigate to the directory where the Subminer script is located.<br>
3. Run the following command: `python subminer.py`.<br>
4. Enter the subdomain or domain name you want to scan when prompted.<br>
5. Choose whether to use a custom DNS server by entering 'y' or 'n'.<br>
6. If you chose to use a custom DNS server, enter the DNS server IP address.<br>
7. Subminer will perform the subdomain scan and display the results.<br>
8. Optionally, choose to save the list of subdomains to a file by entering 'y' or 'n' when prompted.<br>
9. If you chose to save the results, provide a filename and select the file type (txt or csv).<br>
10. Subminer will save the subdomains and IP addresses (if available) to the specified file.<br>

<br>Note: It is recommended to use Subminer responsibly and with permission, respecting the terms of service and legal considerations.
