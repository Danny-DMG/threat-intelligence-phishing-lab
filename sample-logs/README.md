# Synthetic Security Logs

## Overview

This directory contains synthetic security events used to develop, test, and validate Wazuh detection rules for the Threat Intelligence & Phishing Detection Lab.

All sample events are created for educational and testing purposes.

## Objectives

- Simulate DNS queries involving suspicious and benign domains.
- Provide repeatable test data for custom Wazuh rules.
- Validate detection accuracy using positive and negative test cases.
- Identify false positives and false negatives.
- Support reproducible detection testing.

## Planned Test Scenarios

| Scenario | Description | Expected Result |
|---|---|---|
| Positive Detection | DNS query for a domain on the lab's test indicator list | Alert |
| Negative Detection | DNS query for a benign domain | No custom threat alert |
| Subdomain Matching | DNS query involving a subdomain of a test indicator | Depends on documented rule logic |
| Case Sensitivity | DNS query using uppercase or mixed-case characters | Match according to normalization rules |
| Malformed Event | Event with missing or invalid fields | No unintended threat alert |

## Example Synthetic Events

### Positive Test

```json
{"event_type":"dns_query","domain":"login-alert.example","host":"SOC-WIN11-01"}
```

### Negative Test

```json
{"event_type":"dns_query","domain":"training.example","host":"SOC-WIN11-01"}
```

These events are illustrative. The first domain is treated as suspicious only because it will be included in our controlled test indicator list.

## Testing Methodology

1. Define the expected behavior of the detection rule.
2. Create synthetic events representing positive and negative scenarios.
3. Submit test events using Wazuh's `wazuh-logtest` utility.
4. Compare actual detection results with expected outcomes.
5. Document failures, false positives, and rule improvements.
6. Retest after modifying detection logic.

## Important Limitations

Synthetic events do not prove that real DNS telemetry is being collected from the Windows endpoint.

Testing custom JSON events validates the rule and decoder behavior. Live endpoint detection will require an appropriately configured log source and additional end-to-end testing.

## Implementation Status

**Status:** Planned.

No synthetic test event files have been created or executed yet.