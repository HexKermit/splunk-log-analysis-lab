# Log Analysis Findings

## Investigation Summary

A log analysis investigation was performed using Linux command-line tools and Splunk SIEM workflows to identify suspicious authentication activity within IIS log data.

## Key Findings

- A high volume of failed authentication attempts was identified using FTP status code 530.
- Linux CLI parsing using gawk, sort, and uniq was used to validate event frequency.
- Splunk log ingestion workflows were used to centralize and analyze IIS log events.
- Source type analysis confirmed IIS log formatting and parsing behavior.
- Authentication event analysis indicated potential brute-force activity against exposed services.

## Investigation Workflow

The investigation combined:
- Linux log parsing
- Splunk ingestion workflows
- Authentication event analysis
- Event correlation
- Failed login investigation

## Analyst Notes

Repeated failed authentication events may indicate password spraying or brute-force activity targeting externally exposed authentication services.

Correlating Linux CLI analysis with Splunk event analysis improved investigation validation and visibility.
