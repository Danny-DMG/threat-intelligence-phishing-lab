# Wazuh Detection Engineering

## Overview

This directory contains custom Wazuh detection rules, decoders, and supporting documentation developed for the Threat Intelligence & Phishing Detection Lab.

The goal is to identify suspicious activity involving domains, URLs, and phishing-related indicators.

## Detection Objectives

- Identify DNS queries associated with known malicious indicators.
- Detect suspicious URL activity in supported security logs.
- Correlate relevant security events with threat intelligence findings.
- Distinguish potentially malicious activity from benign events.
- Reduce false positives through testing and rule refinement.

## Detection Development Workflow

1. Define the suspicious behavior or indicator to detect.
2. Identify the required log source and event fields.
3. Develop the appropriate Wazuh decoder or detection rule.
4. Test the detection using synthetic events.
5. Validate expected alerts and non-alerting behavior.
6. Document results, limitations, and improvements.

## Testing Approach

Custom detection rules will initially be tested using Wazuh's `wazuh-logtest` utility.

Testing will include:

- **Positive tests:** Events expected to trigger a detection.
- **Negative tests:** Benign events that should not trigger the detection.
- **Edge cases:** Events used to identify unexpected matching behavior.

After successful testing, rules may be deployed to the lab's Wazuh manager for further validation.

## Implementation Status

**Status:** Planned.

No custom threat intelligence or phishing detection rules have been implemented yet.