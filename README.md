# OriginHunt

![originHunt1](https://github.com/user-attachments/assets/bdaa465d-46ee-4a23-9282-716a2a30454c)

OriginHunt is an advanced reconnaissance tool designed to uncover the real IP addresses behind CDN-protected websites. By leveraging multiple attack vectors, it helps penetration testers and security researchers reveal hidden backend servers efficiently.

## Features

- Uncovers real IPs of websites behind Cloudflare, Akamai, Fastly, and other CDNs
- Supports multiple techniques: historical DNS analysis, subdomain enumeration, SSL certificate scanning, and HTTP header analysis
- Integrates with **Shodan** and **Censys** for deeper intelligence gathering
- Multi-threaded scanning for speed and efficiency
- Simple and flexible command-line interface

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/5u5urrus/originhunt.git
cd originhunt
```

## Usage

Basic usage:

```bash
./originhunt -target example.com
./originhunt example.com
```

Advanced options:

```bash
./originhunt -target example.com -threads 20 -timeout 10 -verbose
```

### Command-line Arguments

| Argument         | Description                                      |
|-----------------|--------------------------------------------------|
| `-target`      | Target domain name protected by CDN (required)   |
| `-threads`     | Number of concurrent threads (default: 10)       |
| `-timeout`     | Request timeout in seconds (default: 5)          |
| `-verbose`     | Enable verbose output                            |
| `-quiet`       | Suppress all output except final results         |
| `-historical`  | Perform historical DNS lookup                    |
| `-subdomains`  | Enable subdomain enumeration                     |
| `-ssl`         | Analyze SSL certificates                         |
| `-headers`     | Inspect HTTP headers for leaks                   |
| `-wafbypass`   | Attempt WAF bypass techniques                    |
| `-output`      | Save results to a file                           |
| `-shodan`      | Use Shodan API (optional)                        |


## How OriginHunt Works

OriginHunt employs several detection strategies, some of which are:

1. **Historical DNS Records Analysis**
   - Uses historical DNS records to uncover previously assigned IP addresses.
2. **SSL Certificate Scanning**
   - Extracts hostnames and IPs from SSL certificates using Censys.
3. **Subdomain Enumeration**
   - Identifies non-CDN-covered subdomains that might reveal backend servers.
4. **HTTP Header Analysis**
   - Examines response headers for misconfigurations exposing origin IPs.
5. **Shodan & Censys Integration**
   - Searches public databases for leaked IP addresses and associated hosts.

## Example Output

<img width="600" alt="Screenshot 2025-03-20 193613" src="https://github.com/user-attachments/assets/0d8273dd-dd42-436f-91a8-9a0a7482a2a9" />
<img width="600" alt="Screenshot 2025-03-20 193613" src="https://github.com/user-attachments/assets/54c45d90-7514-4f47-baa1-9c07633aa0fb" />
<img width="600" alt="Screenshot 2025-03-20 193529" src="https://github.com/user-attachments/assets/b5ab3c86-06dd-4024-8cdf-b42043c504f2" />

## Best Practices

To maximize the effectiveness of OriginHunt:

- **Verify discovered IP addresses** using additional fingerprinting techniques.
- **Use responsibly**—ensure compliance with ethical hacking standards.
- **Enhance security**—recommend origin IP protection measures to clients.

## Contributing

Contributions are welcome! Feel free to submit a pull request.

## License

Right now this tool is distributed in binary form only. You may use this software for personal or educational purposes. 
Redistribution, reverse engineering, and modification are prohibited. Commercial use requires written permission from the author.

## Author

Vahe Demirkhanyan  
[LinkedIn](https://www.linkedin.com/in/vahearamian/)
