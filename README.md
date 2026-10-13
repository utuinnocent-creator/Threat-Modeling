# Threat Modeling Report

## Overview
I documented a STRIDE-based threat modeling analysis for AutoDrive’s cloud platform supporting connected and autonomous vehicles. My goal was to identify security risks that could impact both data privacy and physical safety.

## Methodology
I applied the **STRIDE framework**:
- **Spoofing** – forged vehicle certificates, credential stuffing
- **Tampering** – malicious OTA firmware updates, telemetry modification
- **Repudiation** – denial of update requests or log access
- **Information Disclosure** – API misconfigurations, TLS interception
- **Denial of Service** – authentication flooding, API abuse
- **Elevation of Privilege** – API key misuse, weak role segmentation

## Key Risks
- Critical: Forged vehicle certificates / credential stuffing  
- High: Firmware tampering during OTA delivery  
- High: API misconfiguration exposing telemetry data  

## Mitigation Strategies
- Enforce **mutual TLS** and **multi-factor authentication**  
- Use **HSM-backed signing keys** for OTA updates  
- Apply **tamper-evident logging** and strict **RBAC**  
- Conduct **regular API audits** and enforce least-privilege access  
- Deploy **DDoS protection** and rate limiting  

## Recommendations
I recommend prioritizing hardening authentication, securing the OTA pipeline, and auditing API configurations. These measures align with ISO/SAE 21434 and strengthen resilience against
