# Sample 001 – bancoltau.com

## Executive Summary

This investigation analyzed a phishing website impersonating **Banco Itaú**. The objective was to identify malicious infrastructure, extract Indicators of Compromise (IOCs), classify the threat, and document the findings following a SOC analyst workflow.

---

# Sample Information

| Field | Value |
|--------|-------|
| Sample ID | 001 |
| Source | PhishTank |
| Threat Type | Brand Impersonation |
| Severity | 🔴 High |
| Confidence | High |
| Status | Malicious |
| Analysis Date | 2026-08-04 |

---

# Target Brand

**Banco Itaú**

---

# PhishTank

| Field | Value |
|--------|-------|
| Status | Online |
| Verification | Unknown |
| Sample ID | 9496648 |

### Evidence

![PRINT - PhishTank](../screnshots/Sample001/PHISHTANK.png)

---

# Landing Page Analysis

The website presents itself as the official Banco Itaú authentication portal and requests the victim's CPF as the initial authentication factor, indicating an attempt to harvest personally identifiable information (PII).

### Evidence

**[PRINT - Página solicitando CPF]**

---

# URL

```
https://bancoltau.com/
```

---

# VirusTotal Analysis

## Detection

The URL/domain was submitted to VirusTotal for reputation analysis.

### Evidence

**[PRINT - VirusTotal Detection]**

---

## Details

| Field | Value |
|--------|-------|
| Domain | bancoltau.com |
| IP Address | 104.21.14.173 |
| ASN | AS13335 |
| Organization | Cloudflare, Inc. |
| Country | US |

### Evidence

**[PRINT - VirusTotal Details]**

---

## Relations

Related infrastructure and associated objects identified by VirusTotal.

### Evidence

**[PRINT - VirusTotal Relations]**

---

# WHOIS Analysis

| Field | Value |
|--------|-------|
| Registrar | Cloudflare, Inc. |
| Registration Date | 2026-07-28 |
| Expiration Date | 2027-07-28 |
| Status | clientTransferProhibited |

### Name Servers

- bowen.ns.cloudflare.com
- leah.ns.cloudflare.com

### Observation

The domain was recently registered, which is consistent with phishing infrastructure that typically has a short operational lifespan.

### Evidence

**[PRINT - WHOIS]**

---

# DNS Analysis (MXToolbox)

| Item | Value |
|------|-------|
| DNS Resolution | Success |
| Name Server | bowen.ns.cloudflare.com |
| Name Server | leah.ns.cloudflare.com |

### Evidence

**[PRINT - MXToolbox DNS Lookup]**

---

## Mail Infrastructure

| Item | Status |
|------|--------|
| MX Record | |
| SPF | |
| DKIM | |
| DMARC | |

### Evidence

**[PRINT - MXToolbox MX Lookup]**

---

# URLScan Analysis

## Summary

| Field | Value |
|--------|-------|
| Main Domain | bancoltau.com |
| Main IP | 172.67.160.25 |
| HTTP Requests | 13 |
| Contacted Domains | 3 |
| Contacted IPs | 3 |
| Verdict | No Classification |

Google Safe Browsing classified the domain as **Malicious**.

### Evidence

**[PRINT - URLScan Summary]**

---

## Network Activity

Observed connections:

- Cloudflare
- Facebook infrastructure

### Evidence

**[PRINT - URLScan Network]**

---

# TLS Certificate

| Field | Value |
|--------|-------|
| HTTPS | Enabled |
| Certificate Issuer | Google Trust Services (WE1) |
| Valid From | 2026-07-28 |
| Valid Until | 2026-10-26 |

### Observation

The presence of a valid TLS certificate does not indicate legitimacy. Attackers frequently use free certificates to increase user trust.

### Evidence

**[PRINT - Certificate]**

---

# ANY.RUN Dynamic Analysis

## Sandbox Summary

Behavior observed during execution.

### Evidence

**[PRINT - ANY.RUN Verdict]**

---

## Process Tree

Processes created during execution.

### Evidence

**[PRINT - ANY.RUN Process Tree]**

---

## Network Connections

Connections established by the sample.

### Evidence

**[PRINT - ANY.RUN Network]**

---

## HTTP Requests

Observed HTTP/HTTPS requests.

### Evidence

**[PRINT - ANY.RUN HTTP Requests]**

---

## DNS Requests

Observed DNS queries.

### Evidence

**[PRINT - ANY.RUN DNS Requests]**

---

## Screenshot

### Evidence

**[PRINT - ANY.RUN Screenshot]**

---

# Indicators of Compromise (IOCs)

| Type | Value |
|------|-------|
| URL | https://bancoltau.com |
| Domain | bancoltau.com |
| IP Address | 104.21.14.173 |
| ASN | AS13335 |
| Registrar | Cloudflare, Inc. |
| Name Server | bowen.ns.cloudflare.com |
| Name Server | leah.ns.cloudflare.com |

---

# MITRE ATT&CK Mapping

| Technique | ID |
|-----------|----|
| Phishing: Spearphishing Link | T1566.002 |
| Masquerading | T1036 |

---

# Threat Assessment

The analyzed domain impersonates Banco Itaú by using a deceptive domain name visually similar to the legitimate banking website.

The domain was recently registered and hosted behind Cloudflare infrastructure. Google Safe Browsing classified the website as malicious.

The phishing page requests the victim's CPF as the first authentication factor, indicating an attempt to harvest sensitive personal information before collecting banking credentials.

Based on the collected evidence, this campaign is classified as **High Severity** with **High Confidence**.

---

# Recommendations

- Block the domain.
- Block associated IP addresses.
- Add the collected IOCs to the SIEM.
- Configure DNS filtering.
- Monitor for typosquatting domains targeting Banco Itaú.
- Notify potentially affected users.

---

# References

- PhishTank
- VirusTotal
- URLScan
- WHOIS
- MXToolbox
- ANY.RUN
- Google Safe Browsing