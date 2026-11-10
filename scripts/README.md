# Threat Intelligence Enrichment Scripts

## Overview

This directory will contain Python scripts developed to support threat intelligence enrichment and suspicious indicator investigations.

The scripts will help automate repetitive tasks commonly performed by Security Operations Center (SOC) analysts.

## Objectives

- Accept domains, URLs, or IP addresses as investigation inputs.
- Validate and normalize indicators before processing.
- Query supported threat intelligence sources.
- Collect reputation and contextual information.
- Handle API errors and rate limits appropriately.
- Generate structured results for analyst review.
- Support future integration with Wazuh.

## Planned Threat Intelligence Sources

- VirusTotal
- AlienVault Open Threat Exchange (OTX)
- URLhaus

Additional sources may be evaluated as the project develops.

## Development Approach

The project will begin with manual threat intelligence investigations to establish a foundational understanding of indicator analysis.

Python automation will be introduced incrementally after the manual investigation workflow has been validated.

Scripts will be developed and tested locally before any integration with the existing Wazuh environment.

## Security Considerations

- Never commit API keys or credentials to GitHub.
- Store secrets in environment variables or excluded local configuration files.
- Use synthetic indicators during initial testing.
- Respect API rate limits and usage restrictions.
- Avoid submitting private organizational information to public intelligence services.
- Treat threat intelligence results as supporting evidence rather than definitive proof of malicious activity.

## Implementation Status

**Status:** Planned.

No enrichment scripts have been implemented yet.