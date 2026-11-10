# Lab Architecture

## Overview

The Threat Intelligence & Phishing Detection Lab is a cybersecurity portfolio project designed to simulate Security Operations Center (SOC) workflows involving suspicious domains, phishing indicators, threat intelligence enrichment, and detection engineering.

This project builds upon an existing Wazuh SOC Home Lab and reuses its security monitoring infrastructure.

## Lab Components

| Component | Purpose |
|---|---|
| Windows 11 Host | Development environment using VS Code, Git, and Python |
| Oracle VirtualBox | Virtualization platform |
| Ubuntu 24.04 VM (SOC-WAZUH-01) | Hosts the Wazuh SIEM |
| Windows 11 VM (SOC-WIN11-01) | Generates simulated security events |
| Wazuh Agent | Collects endpoint security telemetry |
| Python | Supports threat intelligence enrichment and automation |
| Threat Intelligence Sources | Provide contextual information about suspicious indicators |
| GitHub | Stores project documentation, scripts, detections, and investigation reports |

## Planned Workflow

1. Generate safe, simulated DNS and URL events.
2. Collect relevant security events using the Wazuh agent.
3. Analyze events using Wazuh detection rules.
4. Investigate suspicious indicators using threat intelligence sources.
5. Enrich findings with reputation and contextual information.
6. Document detection results and investigation conclusions.

## Design Principles

- Reuse existing lab infrastructure where practical.
- Prioritize free and open-source tools.
- Use synthetic data and safe testing methods.
- Protect API keys and sensitive information.
- Validate detections before deploying them.
- Document technical decisions and investigation findings.

## Implementation Status

**Status:** Architecture planning and repository initialization.

The architecture is proposed and has not yet been fully validated or implemented.

## Production Deployment and Shared Responsibilities

In a production Security Operations Center (SOC), effective threat detection requires coordination between internal IT teams, Managed Service Providers (MSPs), and Managed Security Service Providers (MSSPs).

### Centralized Endpoint Configuration

Sysmon can be deployed and managed across Windows endpoints using centralized management platforms such as Group Policy, Microsoft Intune, or Microsoft Configuration Manager.

These tools can distribute standardized Sysmon configurations and updates without requiring administrators to configure each endpoint manually.

### Centralized Security Monitoring

Wazuh agents collect endpoint telemetry and forward relevant events to the Wazuh manager.

Wazuh's centralized agent configuration allows administrators to manage log collection settings across groups of endpoints.

Detection rules are configured on the Wazuh manager and evaluated against collected security events.

### Shared Responsibilities

Responsibilities vary depending on the organization's service agreements and operating model.

| Responsibility | Typical Owner |
|---|---|
| Approve production changes | Authorized internal IT or business owner |
| Deploy and maintain Sysmon | Internal IT / MSP |
| Configure Wazuh agent log collection | Internal IT / MSP / MSSP |
| Develop and tune SIEM detections | MSSP / SOC |
| Validate end-to-end detection | MSSP / SOC with IT support |
| Investigate security alerts | SOC / MSSP |
| Coordinate remediation | Internal IT / MSP / authorized incident responders |

### Telemetry Validation and Troubleshooting

Successful deployment does not automatically guarantee effective monitoring.

When endpoints are missing expected security telemetry, troubleshooting should verify each stage of the collection pipeline:

1. Confirm Sysmon is installed, running, and generating the expected events.
2. Verify the Wazuh agent is running and configured to collect the appropriate event channels.
3. Confirm the agent is successfully communicating with the Wazuh manager.
4. Verify events are received and decoded correctly.
5. Validate that detection rules generate alerts for appropriate test events.

An event may be successfully collected without generating an alert if no applicable detection rule matches.

### Operational Considerations

Production deployments should include:

- Defined responsibilities and change approval procedures.
- Standardized endpoint configurations.
- Telemetry coverage monitoring.
- Detection testing and false-positive tuning.
- Documented escalation and incident response procedures.
- Periodic configuration reviews and validation.

This project demonstrates these concepts in a controlled lab environment. Production deployment considerations are documented for educational purposes and have not been implemented in an organizational environment.