# Home Server Security Lab (Ubuntu Server)

This repository documents a self-hosted home server running on **Ubuntu Server**, designed as a foundational **security operations and monitoring lab**. The primary focus of the environment is centralized log collection, endpoint telemetry, and security monitoring using an in-house SIEM deployment.

The lab is intentionally minimal and production-minded, emphasizing secure configuration, observability, and clear documentation over tool sprawl.

---

## Environment Overview

- **Operating System:** Ubuntu Server (LTS)
- **Primary Role:** Security monitoring and log aggregation
- **Secondary Role:** Personal network-attached storage (NAS)
- **Deployment Model:** Docker-based services with host-level hardening

---

## Core Components

### Wazuh SIEM (Dockerized)

The server runs **Wazuh** inside Docker as a centralized SIEM platform to receive, analyze, and alert on security telemetry from endpoint agents.

**Capabilities:**
- Centralized log ingestion from agents
- Security event correlation and alerting
- Authentication and authorization monitoring
- File integrity monitoring (agent-side)
- Host-based intrusion detection

**Architecture Highlights:**
- Wazuh Manager and supporting components run in containers
- Agents forward telemetry to the server over secure channels
- Logs are retained locally for analysis and tuning
- Configuration and deployment are container-managed for consistency

This setup mirrors small-to-mid scale SOC environments and provides a realistic platform for detection engineering and incident response experimentation.

---

### Network-Attached Storage (NAS)

The server also functions as a **personal file server** for internal storage.

**Characteristics:**
- Not internet-facing
- Access restricted to trusted internal devices
- Used for document storage, backups, and lab artifacts
- Operates independently of SIEM services

The NAS component is intentionally simple and segregated to avoid unnecessary attack surface expansion.

---

## Security Considerations

- Minimal exposed services
- Docker used to isolate SIEM components
- Principle of least privilege applied to services where possible
- Separation between security tooling and personal storage
- Focus on visibility before automation

This lab prioritizes **secure-by-default configuration** and observability over aggressive exposure or experimental services.
No sensitive data, credentials, or environment-specific secrets are committed to this repository.

---

## Planned Enhancements 

Future additions may include:
- Expanded endpoint agent coverage
- Custom detection rules and alert tuning
- Threat intelligence enrichment
- Controlled attack telemetry for detection validation
- Incident response playbooks and automation



