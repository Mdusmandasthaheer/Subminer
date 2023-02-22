import argparse
import socket
import re
import requests
import csv
import pyfiglet

Subminer= pyfiglet.figlet_format('Subminer')
print(Subminer)
print("                               by usman")



# Define the URL to use for the search
url = input("\nEnter the subdomain to search for [subdomains] \n\n# ")

# Add https://www. to the URL if it's not already present
if not url.startswith("https://www."):
    url = "https://www." + url

# Prompt the user for custom DNS
custom_dns = input("\nWould you like to use custom DNS? [y/n]-> ")
if custom_dns.lower() == "y":
    dns_server = input("\nEnter the custom DNS server\n\n# ")
else:
    dns_server = None

#  the User-Agent header to use in the requests
headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3'
}

# Send an HTTP GET request to the URL and get the response HTML
response = requests.get(url, headers=headers)
html = response.text

# Use regex to find all subdomains in the response HTML
regex = r"(?<=\/\/)([\w.-]+)\b"
matches = re.findall(regex, html)

# Add each unique subdomain found to the subdomains list
subdomains = []
for match in matches:
    if match not in subdomains:
        subdomains.append(match)

# Output the list of subdomains found
if subdomains:
    subdomains.sort()
    print(f"\nSubdomains found for {url}\n")
    for subdomain in subdomains:
        print(subdomain)
else:
    print(f"No subdomains found for {url}")

# Prompt the user to save the list of subdomains to a file
save_file = input("\nWould you like to save the list of subdomains to a file? [y/n]-> ")
if save_file.lower() == "y":
    # Ask the user for the filename and file type
    filename = input("\nEnter a filename for the subdomains\n->")
    file_type = input("\nEnter the file type (txt or csv): ")

    # Check if the file type is valid
    if file_type.lower() not in ['txt', 'csv']:
        print("Invalid file type.")
    else:
        # Save the subdomains to the file
        with open(filename + '.' + file_type, 'w', newline='') as file:
            if file_type.lower() == 'csv':
                writer = csv.writer(file)
                writer.writerow(['Subdomain', 'IP Address'])
                for subdomain in subdomains:
                    try:
                        ip = socket.gethostbyname(subdomain)
                    except:
                        ip = "N/A"
                    writer.writerow([subdomain, ip])
            else:
                for subdomain in subdomains:
                    try:
                        ip = socket.gethostbyname(subdomain)
                    except:
                        ip = "N/A"
                    file.write(subdomain + " , " + ip + "\n")
        print("\nSubdomains listed successfully and saved to file.")
else:
    print("\nSubdomains listed successfully.")
