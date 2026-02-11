# SSH-Log-Analysis-Splunk
SOC Analyst project analyzing SSH authentication logs using Splunk to detect brute-force attacks, failed logins, successful access, and suspicious connections.

# SSH Log Analysis Using Splunk

## Project Overview
This project demonstrates the analysis of SSH authentication logs using Splunk to identify suspicious activity and potential security threats. The workflow reflects real-world SOC Analyst responsibilities including log ingestion, parsing, analysis, visualization, and alerting.

---

## Objective
The objective of this project is to detect and analyze:

- Successful SSH login attempts
- Failed SSH authentication attempts
- Multiple failed authentication attempts indicating brute-force attacks
- SSH connections without authentication indicating scanning or probing activity

---

## Lab Setup and Prerequisites
- Splunk Enterprise or Free Edition
- SSH log file (`ssh_log.json`)
- Completed Splunk installation and basic configuration


##Step-by-Step Guide
Task 1: Ingest and Parse Logs
Upload ssh_log.json into Splunk.
Ensure the following fields are extracted correctly:
event_type (Successful SSH Login, Failed SSH Login, Multiple Failed Authentication Attempts, Connection Without Authentication)
auth_success (true/false/null)
auth_attempts
id.orig_h (source IP)
id.resp_h (destination host)
Run a validation search:
- index=ssh_log | stats count by event_type

