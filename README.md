# AWS Cloud SIEM & SOC Lab

## Overview

This project is a hands-on cybersecurity lab designed to simulate a small Security Operations Center (SOC) environment in Amazon Web Services (AWS).

The environment uses Wazuh as the Security Information and Event Management (SIEM) platform to collect, analyze, and investigate security events from Windows and Linux endpoints, as well as AWS cloud activity.

The goal of this project is to gain practical experience with security monitoring, log analysis, threat detection, incident investigation, and cloud security.

## Architecture

```mermaid
flowchart TD

    A[AWS SIEM / SOC Lab]
    B[AWS VPC<br>10.0.0.0/16]
    C[Public Subnet<br>10.0.1.0/24]

    D[Windows Endpoint<br>Wazuh Agent]
    E[Linux Endpoint<br>Wazuh Agent]

    F[Wazuh SIEM Server]
    G[Wazuh Dashboard]
    H[Security Investigations<br>& Incident Response]

    I[AWS CloudTrail<br>Account Activity Logs]
    J[Amazon S3<br>CloudTrail Logs]

    A --> B
    B --> C

    C --> D
    C --> E

    D -->|Security/Event Logs| F
    E -->|Security/Event Logs| F

    I -->|AWS Logs| J
    J -->|CloudTrail Logs| F

    F --> G
    G --> H
```

## Objectives

* Deploy a SIEM platform in AWS
* Configure a secure AWS virtual network
* Deploy and configure Wazuh
* Monitor Windows and Linux endpoints
* Collect and analyze authentication events
* Detect file and system changes
* Monitor AWS activity using CloudTrail
* Investigate simulated security incidents
* Map detections to the MITRE ATT&CK framework
* Document incident investigations
* Practice SOC analyst workflows

## Technologies

| Technology                | Purpose                        |
| ------------------------- | ------------------------------ |
| Amazon Web Services (AWS) | Cloud infrastructure           |
| Amazon EC2                | Virtual machines               |
| Amazon VPC                | Network isolation              |
| AWS IAM                   | Identity and access management |
| AWS CloudTrail            | AWS activity logging           |
| Amazon S3                 | CloudTrail log storage         |
| Wazuh                     | SIEM / security monitoring     |
| Windows                   | Endpoint monitoring            |
| Linux                     | Endpoint monitoring            |
| GitHub                    | Project documentation          |
| MITRE ATT&CK              | Threat behavior mapping        |


## Planned Security Scenarios

### Scenario 1: Authentication Failures

Generate multiple failed authentication attempts and investigate the resulting SIEM alerts.

**Objective:** Practice identifying suspicious authentication activity.

### Scenario 2: Unauthorized Account Creation

Create a test account on a lab endpoint and investigate the corresponding security event.

**Objective:** Practice monitoring account-management activity.

### Scenario 3: File Integrity Monitoring

Modify a monitored file and investigate the resulting Wazuh alert.

**Objective:** Practice detecting unauthorized file changes.

### Scenario 4: PowerShell Activity

Generate controlled PowerShell activity on the Windows endpoint and investigate the resulting telemetry.

**Objective:** Practice Windows security monitoring and threat detection.

### Scenario 5: AWS Activity

Generate controlled AWS IAM or infrastructure activity and investigate the corresponding CloudTrail event.

**Objective:** Practice cloud security monitoring.

## Incident Investigation Methodology

Each security event will be investigated using the following process:

1. Identify the alert
2. Determine the affected host or AWS resource
3. Examine the available logs
4. Establish a timeline
5. Determine the nature of the activity
6. Identify relevant MITRE ATT&CK techniques
7. Determine an appropriate response
8. Document findings
9. Identify lessons learned

## Project Structure

```text
aws-siem-lab/
│
├── README.md
│
├── architecture/
│   └── architecture.png
│
├── documentation/
│   ├── deployment.md
│   ├── aws-monitoring.md
│   └── investigations/
│
├── detections/
│   └── custom-rules/
│
├── screenshots/
│
└── incident-reports/
    ├── incident-001.md
    ├── incident-002.md
    └── incident-003.md
```

## Security Considerations

This project is intended for an isolated educational environment.

No real credentials, private keys, passwords, API keys, tokens, or other sensitive information will be committed to this repository.

AWS resources will be restricted using security groups, IAM permissions, and network controls.

Security testing will be performed only against systems owned and controlled as part of this lab.

## Project Status

**Current Phase:** Project initialization

* [x] Create GitHub repository
* [x] Define project architecture
* [x] Build AWS VPC
* [ ] Deploy Wazuh SIEM
* [ ] Deploy Windows endpoint
* [ ] Deploy Linux endpoint
* [ ] Configure Wazuh agents
* [ ] Configure AWS CloudTrail
* [ ] Integrate AWS logs
* [ ] Perform security investigations
* [ ] Document incidents
* [ ] Finalize portfolio documentation

## Skills Demonstrated

This project will demonstrate practical experience with:

* SIEM deployment
* Security monitoring
* Log analysis
* Incident investigation
* Endpoint security
* Windows security
* Linux security
* AWS security
* IAM
* CloudTrail
* Network security
* Threat detection
* MITRE ATT&CK
* SOC workflows
* Technical documentation



