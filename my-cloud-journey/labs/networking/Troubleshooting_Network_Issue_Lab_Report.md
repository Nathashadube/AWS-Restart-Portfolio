# Troubleshooting a Network Issue Lab Report

# Troubleshooting a Network Issue Lab Report

## Student Name
_________________________

## Student Number
_________________________

## Module
_________________________

## Practical Title
Troubleshooting a Network Issue in Amazon EC2

## Date
_________________________

---

# 1. Introduction

Network troubleshooting is an essential skill for system administrators and cloud engineers. It involves identifying, diagnosing, and resolving issues that prevent systems and services from functioning correctly.

In this lab, an Amazon EC2 instance was used to troubleshoot a web server service. The Apache HTTP Server (`httpd`) was inspected to determine its operational status. The service was found to be inactive and was subsequently started and verified to ensure that the web server was functioning correctly.

---

# 2. Objective

The objectives of this lab were:

- To identify the status of the Apache web server.
- To troubleshoot a service-related network issue.
- To start a stopped service using system management commands.
- To verify that the service was running successfully.
- To understand the use of Linux service management tools.

---

# 3. Environment

### Platform
Amazon EC2 (Amazon Linux 2)

### User Account
`ec2-user`

### Service Tested
Apache HTTP Server (`httpd`)

### Commands Used

```bash
sudo systemctl status httpd.service
sudo systemctl start httpd.service
```

---

# 4. Task 1: Verify Apache Service Status

### Command Executed

```bash
sudo systemctl status httpd.service
```

### Purpose

The purpose of this command was to determine whether the Apache web server was running on the EC2 instance.

### Screenshot Evidence

![Apache Service Status](CaptureA.PNG)

### Results

The command output indicated:

```text
Active: inactive (dead)
```

### Analysis

The status output revealed that the Apache HTTP service was installed on the server but was not currently running. Since the web server was inactive, users would be unable to access hosted web pages or applications.

This confirmed the existence of a service-related issue requiring corrective action.

### Conclusion

The initial troubleshooting step successfully identified that the Apache service was stopped.

---

# 5. Task 2: Start the Apache Service

### Command Executed

```bash
sudo systemctl start httpd.service
```

### Purpose

The purpose of this command was to start the Apache HTTP Server and restore web service functionality.

### Results

The command executed successfully without returning any error messages.

### Analysis

A successful execution indicated that the operating system accepted the command and attempted to start the web server process.

### Conclusion

The Apache service was successfully started.

---

# 6. Task 3: Verify Service Recovery

### Command Executed

```bash
sudo systemctl status httpd.service
```

### Purpose

The command was executed again to confirm that the Apache service was running correctly after being started.

### Results

The status output displayed:

```text
Active: active (running)
```

Additional information included:

- Main Process ID (PID) assigned.
- Apache worker processes running.
- Service startup confirmation messages.
- Systemd status showing successful service activation.

### Analysis

The output confirmed that:

- The Apache service was operational.
- The web server process was running normally.
- Worker processes were active and ready to handle requests.
- The network service issue had been resolved successfully.

### Conclusion

The Apache web server was restored to a healthy operational state.

---

# 7. Troubleshooting Summary

| Task | Command | Result | Status |
|--------|---------|---------|---------|
| Check Service Status | `sudo systemctl status httpd.service` | Service inactive | Identified |
| Start Service | `sudo systemctl start httpd.service` | Service started successfully | Completed |
| Verify Service | `sudo systemctl status httpd.service` | Service active and running | Passed |

---

# 8. Findings

The troubleshooting process revealed that the network issue was not caused by connectivity problems but by a stopped web service. By examining the service status and restarting the Apache HTTP Server, normal service operation was restored.

The `systemctl` utility proved to be an effective tool for managing Linux services and diagnosing service availability issues.

---

# 9. Conclusion

The Troubleshooting a Network Issue lab was completed successfully. The Apache HTTP Server was initially found to be inactive, which would have prevented users from accessing hosted web resources. Through the use of Linux service management commands, the issue was identified and corrected.

This exercise demonstrated the importance of systematic troubleshooting techniques and reinforced practical skills in managing and recovering network services within a cloud computing environment.

---

# 10. Screenshot Reference

**Figure 1:** Apache HTTP Server status before and after troubleshooting.

![Apache Service Troubleshooting](CaptureA.PNG)

---
