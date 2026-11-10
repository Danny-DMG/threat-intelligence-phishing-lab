# Technical Documentation

This directory contains technical documentation supporting the Threat Intelligence & Phishing Detection Lab.

## Purpose

The goal of this directory is to document the implementation, configuration, troubleshooting, and maintenance procedures used throughout the project.

These documents will help demonstrate an understanding of the technologies involved and provide reproducible instructions for building and maintaining the lab.

## Planned Documentation

### Lab Setup and Configuration

- Wazuh manager and agent configuration
- Sysmon installation and DNS event logging
- Wazuh log collection and centralized agent configuration
- Custom decoder and detection rule configuration
- Python environment setup and dependency management

### Threat Intelligence Integration

- Threat intelligence source selection
- API configuration and authentication
- Indicator enrichment workflows
- Data normalization and enrichment output
- API rate limits and error handling

### Testing and Validation

- Synthetic event generation
- Detection rule testing with `wazuh-logtest`
- Real endpoint telemetry validation
- End-to-end detection testing
- False-positive analysis and detection tuning

### Troubleshooting and Maintenance

- Common configuration issues
- Agent connectivity and log collection troubleshooting
- Detection rule troubleshooting
- Python script errors and debugging
- Configuration updates and maintenance procedures

## Documentation Standards

Technical documentation should:

1. Explain the purpose of each configuration or procedure.
2. Provide clear, reproducible steps.
3. Include relevant commands and configuration examples.
4. Explain how to verify successful implementation.
5. Document troubleshooting steps and known limitations.
6. Reference supporting screenshots when appropriate.
7. Avoid exposing credentials, API keys, personal information, or organizational data.

## Documentation Status

Technical guides will be added as the lab is developed, configured, tested, and validated.