# Traffic Capture and Security Analysis Using Wireshark

## CS 3093 - Cryptography & Network Security - Final Project

### Project Overview
This project focuses on setting up a safe virtual lab environment, capturing network traffic using Wireshark, and analyzing TCP/IP, HTTP, and web application behavior in a vulnerable web application (OWASP Juice Shop). The goal is to identify common security issues such as plaintext credentials, exposed session tokens, and lack of encryption.

### Objectives
- [x] Set up virtual lab environment with Kali Linux and OWASP Juice Shop
- [x] Capture network traffic using Wireshark
- [x] Analyze TCP handshake and HTTP traffic
- [x] Identify security vulnerabilities (credentials exposure, session token exposure)
- [x] Provide security recommendations
- [x] Document findings and reflections

### Key Findings
1. **Credentials Exposure**: Login credentials transmitted in plaintext via HTTP
2. **Session Token Exposure**: Session cookies visible in every request
3. **Lack of Encryption**: No TLS/HTTPS implementation
4. **Insecure Cookies**: Missing Secure, HttpOnly, and SameSite flags

### Tools & Technologies
- **Wireshark**: Network protocol analyzer
- **VirtualBox**: Virtualization software
- **Kali Linux**: Penetration testing distribution
- **OWASP Juice Shop**: Vulnerable web application
- **Ubuntu 24.04**: Target server OS

### Repository Structure
```
CS3093-crypto-network-security-final-project/
├── report/
│   └── CryptoFinalproj.pdf              # Complete project report
├── pcaps/
│   └── traffic_capture.pcapng           # Wireshark network capture file
├── screenshots/                         # Analysis screenshots
│   ├── tcp-handshake.png                # TCP three-way handshake
│   ├── http-post-login-plaintext.png    # Plaintext credentials exposure
│   └── session-cookie-exposure.png      # Session cookie in traffic
├── LICENSE                              # MIT License file
├── .gitignore                           # Git ignore rules
└── README.md                            # Project documentation

```

### Analysis Details
- **Capture Duration**: 3-4 minutes
- **Interface**: eth0 on Kali VM
- **Network Configuration**: Bridged networking
- **Filters Used**: `http`, `http.request.method == "GET"`, `http.cookie`

### Recommendations
1. **Implement HTTPS/TLS** for all communications
2. **Secure Cookies** with Secure, HttpOnly, and SameSite flags
3. **Improve Session Management** with token regeneration
4. **Harden Application** by disabling debug modes and sanitizing inputs


## Contributors

- Sarah Eid | [Abeer Hussain](https://github.com/abeerahrar) | Nancy Elhaddad 
- Effat University, College of Engineering, Computer Science Department

### License
This project is for educational purposes as part of CS 3093 at Effat University.
