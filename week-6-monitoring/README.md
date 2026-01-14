# Week 6: Monitoring & Observability

## 1. Project Overview
This module focuses on implementing monitoring and observability within an Azure environment using native Azure monitoring services. The objective was to gain hands-on experience collecting metrics, logs, and activity data to support operational visibility, troubleshooting, and basic security monitoring.

The lab emphasizes how monitoring supports reliability, performance, and security in cloud environments.

---

## 2. Cloud & Security Rationale
Effective monitoring is critical for detecting performance issues, misconfigurations, and potential security events. In cloud environments, visibility is achieved through centralized logging, metrics collection, and alerting rather than traditional host-based monitoring.

This module aligns with:
- Shared Responsibility Model (customer responsibility for monitoring and response)
- Security Operations (SecOps) and Site Reliability Engineering (SRE) fundamentals
- Early detection of abnormal or unauthorized activity

---

## 3. Implemented Azure Services & Controls

### A. Azure Monitor
- Metrics Collection: Reviewed platform metrics for Azure resources to assess health and performance.
- Activity Logs: Analyzed subscription-level activity logs for administrative and operational actions.
- Centralized Visibility: Used Azure Monitor as the primary monitoring interface.

---

### B. Log Analytics
- Log Analytics Workspace: Created and configured a workspace for centralized log storage.
- Resource Integration: Connected Azure resources to send diagnostic logs.
- Querying Logs: Executed basic Kusto Query Language (KQL) queries to analyze operational data.
- Log Retention Awareness: Reviewed log retention settings and cost considerations.

---

### C. Alerts & Diagnostics
- Diagnostic Settings: Enabled diagnostic logging for supported resources.
- Alert Rules: Reviewed alert configuration concepts for metrics and log-based alerts.
- Operational Awareness: Evaluated how alerts support proactive issue detection.

---

## 4. Operational Metrics

- Monitoring Coverage:
  - 100% of selected resources integrated with Azure Monitor
  - Diagnostic logs successfully forwarded to Log Analytics

- Log Visibility:
  - Activity logs captured for administrative actions
  - Resource-level logs available for analysis

- Query Validation:
  - Successfully executed KQL queries to filter and analyze log data
  - Verified log ingestion and timestamp accuracy

- Security & Operations:
  - Improved visibility into configuration changes
  - Established baseline monitoring for future security investigations

---

## 5. Key Outcomes
- Gained practical experience using Azure Monitor and Log Analytics
- Understood the relationship between metrics, logs, and alerts
- Learned basic KQL querying for operational insights
- Built foundational monitoring skills applicable to cloud operations and security roles

---

# Week 6: Monitoring & Observability

## 1. Project Overview
This module focuses on implementing monitoring and observability within an Azure environment using native Azure monitoring services. The objective was to gain hands-on experience collecting metrics, logs, and activity data to support operational visibility, troubleshooting, and basic security monitoring.

The lab emphasizes how monitoring supports reliability, performance, and security in cloud environments.

---

## 2. Cloud & Security Rationale
Effective monitoring is critical for detecting performance issues, misconfigurations, and potential security events. In cloud environments, visibility is achieved through centralized logging, metrics collection, and alerting rather than traditional host-based monitoring.

This module aligns with:
- Shared Responsibility Model (customer responsibility for monitoring and response)
- Security Operations (SecOps) and Site Reliability Engineering (SRE) fundamentals
- Early detection of abnormal or unauthorized activity

---

## 3. Implemented Azure Services & Controls

### A. Azure Monitor
- Metrics Collection: Reviewed platform metrics for Azure resources to assess health and performance.
- Activity Logs: Analyzed subscription-level activity logs for administrative and operational actions.
- Centralized Visibility: Used Azure Monitor as the primary monitoring interface.

---

### B. Log Analytics
- Log Analytics Workspace: Created and configured a workspace for centralized log storage.
- Resource Integration: Connected Azure resources to send diagnostic logs.
- Querying Logs: Executed basic Kusto Query Language (KQL) queries to analyze operational data.
- Log Retention Awareness: Reviewed log retention settings and cost considerations.

---

### C. Alerts & Diagnostics
- Diagnostic Settings: Enabled diagnostic logging for supported resources.
- Alert Rules: Reviewed alert configuration concepts for metrics and log-based alerts.
- Operational Awareness: Evaluated how alerts support proactive issue detection.

---

## 4. Operational Metrics

- Monitoring Coverage:
  - 100% of selected resources integrated with Azure Monitor
  - Diagnostic logs successfully forwarded to Log Analytics

- Log Visibility:
  - Activity logs captured for administrative actions
  - Resource-level logs available for analysis

- Query Validation:
  - Successfully executed KQL queries to filter and analyze log data
  - Verified log ingestion and timestamp accuracy

- Security & Operations:
  - Improved visibility into configuration changes
  - Established baseline monitoring for future security investigations

---

## 5. Key Outcomes
- Gained practical experience using Azure Monitor and Log Analytics
- Understood the relationship between metrics, logs, and alerts
- Learned basic KQL querying for operational insights
- Built foundational monitoring skills applicable to cloud operations and security roles

---


## 7. Cleanup & Cost Management
- Reviewed log retention periods to avoid unnecessary storage costs
- Removed monitoring resources after validation
- Deleted the resource group to prevent ongoing charges

---

## 8. Key Takeaways
- Monitoring is essential for reliability, performance, and security
- Azure Monitor provides centralized visibility across Azure resources
- Log Analytics enables powerful analysis through KQL
- Early detection and observability reduce operational and security risks



