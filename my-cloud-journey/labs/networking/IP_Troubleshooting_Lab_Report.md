# Internet Protocol Troubleshooting Commands Lab Report

## Practical Title
Internet Protocol (IP) Troubleshooting Commands Lab

---

# 1. Introduction

The purpose of this lab was to perform basic Internet Protocol (IP) troubleshooting on an Amazon EC2 Linux instance. Various networking commands were executed to verify network connectivity, test communication with external hosts, and diagnose potential network issues.

The commands used included:

- `ping`
- `telnet`
- `curl`

These commands are commonly used by system administrators and network engineers to troubleshoot connectivity problems and verify network services.

---

# 2. Objective

The objectives of this lab were:

- To verify network connectivity from an EC2 instance.
- To test communication with external hosts.
- To confirm access to internet-based services.
- To understand the use of common network troubleshooting tools.

---

# 3. Environment

### Platform
Amazon EC2 (Amazon Linux 2)

### User Account
`ec2-user`

### Network Testing Tools
- Ping
- Telnet
- Curl

---

# 4. Task 1: Verify Internet Connectivity Using Ping

### Command Executed

```bash
ping 8.8.8.8 -c 5
```

### Purpose

The `ping` command was used to test network connectivity between the EC2 instance and Google's public DNS server (8.8.8.8).

### Screenshot Evidence

<img src="restart/labs/Capture2.PNG">

### Results

The command successfully transmitted and received five packets.

### Analysis

The successful responses indicate that the EC2 instance has internet connectivity, network routing is functioning correctly, there is no packet loss, and the connection is stable.

---

# 5. Task 2: Verify TCP Connectivity Using Telnet

### Command Executed

```bash
telnet www.google.com 80
```

### Purpose

The `telnet` command was used to verify connectivity to Google's web server over TCP port 80 (HTTP).

### Screenshot Evidence

![Telnet Test](Capture4.PNG)

### Results

A successful connection was established to Google's web server.

### Analysis

The successful connection demonstrates that DNS resolution is functioning correctly, TCP communication is working, and outbound web traffic is permitted.

---

# 6. Task 3: Test Web Access Using Curl

### Command Executed

```bash
curl -vLo /dev/null https://aws.com
```

### Purpose

The `curl` command was used to test HTTPS communication with an external website and inspect the HTTP response.

### Results

The server returned an HTTP response indicating that communication was successfully established.

### Analysis

Although a "400 Bad Request" response was received, it confirms successful DNS resolution, HTTPS connectivity, and data exchange between the EC2 instance and the remote server.

---

# 7. Summary of Findings

| Test | Command | Result | Status |
|--------|---------|---------|---------|
| Network Connectivity | `ping 8.8.8.8 -c 5` | Successful replies received | Passed |
| TCP Connectivity | `telnet www.google.com 80` | Connection established | Passed |
| HTTPS Connectivity | `curl -vLo /dev/null https://aws.com` | Server responded | Passed |

---

# 8. Overall Conclusion

The Internet Protocol troubleshooting exercises were successfully completed on the Amazon EC2 instance. The results confirmed internet connectivity, DNS resolution, TCP communication capability, and access to external web services.
