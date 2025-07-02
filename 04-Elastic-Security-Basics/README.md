# Elastic Security: Basics

## Lab Overview

This comprehensive lab introduces the fundamentals of Elastic Security, covering the complete SOC analyst workflow from data exploration to threat investigation. You'll learn to navigate Kibana's security features, analyze authentication events, investigate network anomalies, and identify real-world threats using practical scenarios.

**Author:** Mykyta Palamarchuk  
**Role Focus:** SOC Analyst | Incident Response Specialist  
**Certification:** CompTIA Security+ (SY0-701)  
**Framework Alignment:** SIEM operations and security event analysis

---

## Learning Objectives

- Master Kibana interface and navigation for security operations
- Perform data discovery and analysis using Kibana's search capabilities
- Utilize Security dashboards for threat detection and monitoring
- Investigate authentication anomalies and network security events
- Conduct practical threat hunting and malware identification
- Apply SOC analyst workflows for incident response

## Kibana Interface Overview

### Welcome Home Screen

Kibana provides specialized solutions across four key domains, each designed for specific operational needs.

![Kibana Welcome Home Screen](assets/screenshots/kibana-welcome-home-screen.png)

**Core Modules:**
- **Enterprise Search:** Internal system searchability and document management
- **Observability:** Application performance monitoring and system health
- **Security:** Threat detection, incident response, and security operations
- **Analytics:** Data exploration, visualization, and business intelligence

### Navigation Structure

Access different Kibana modules through the comprehensive navigation menu.

![Kibana Main Navigation Menu](assets/screenshots/kibana-main-navigation-menu.png)

**Navigation Hierarchy:**
- **Home:** Central dashboard and module access
- **Analytics:** Data exploration and visualization tools
- **Security:** Comprehensive security operations center
- **Management:** System configuration and administration

---

## Analytics and Data Discovery

### Analytics Navigation

The Analytics module provides powerful tools for data exploration and analysis.

![Analytics Navigation Menu](assets/screenshots/analytics-navigation-menu.png)

**Key Analytics Features:**
- **Discover:** Ad-hoc data searching and exploration
- **Dashboard:** Visualization and metrics compilation
- **Canvas:** Custom presentation and reporting
- **Machine Learning:** Anomaly detection and predictive analytics

### Discover Interface

Use Discover for advanced data exploration and event investigation.

![Discover Interface Full View](assets/screenshots/discover-interface-full-view.png)

**Discovery Capabilities:**
- **Time-based Analysis:** Configurable time range filtering
- **Index Pattern Selection:** Multiple data source access
- **Field Customization:** Dynamic column configuration
- **Interactive Visualization:** Histogram-based event distribution

### Authentication Event Analysis

Investigate authentication events to identify potential security threats.

![Discover Search Interface Authentication](assets/screenshots/discover-search-interface-authentication.png)

**Search Configuration:**
- **Index Pattern:** `auditbeat-*` for system events
- **Query:** `event.category: "authentication"`
- **Time Range:** Today's events for current analysis
- **Filter:** `source.ip: exists` to identify source origins

### Event Detail Investigation

Examine individual events for comprehensive threat analysis.

![Discover Authentication Event Details](assets/screenshots/discover-authentication-event-details.png)

**Critical Findings:**
- **Source IP:** `5.188.62.102` generating authentication events
- **Event Type:** Failed authentication attempts
- **Pattern Analysis:** Potential brute force attack indicators
- **Investigative Action:** Correlation with network security alerts

---

## Dashboard Analytics

### Suricata Network Monitoring

Monitor network protocols and traffic patterns using specialized dashboards.

![Filebeat Suricata Dashboard Overview](assets/screenshots/filebeat-suricata-dashboard-overview.png)

**Network Analysis Results:**
- **Most Popular Protocol:** DNS (Domain Name System)
- **Traffic Distribution:** Protocol usage patterns and anomalies
- **Event Timeline:** Temporal analysis of network activities
- **Geographic Distribution:** Connection source and destination mapping

---

## Security Operations Center

### Security Module Navigation

Access comprehensive security features through the dedicated Security module.

![Security Navigation Menu](assets/screenshots/security-navigation-menu.png)

**Security Module Components:**
- **Overview:** Central security dashboard and threat intelligence
- **Detect:** Alert management and detection rule configuration
- **Explore:** Host and network security analysis
- **Investigate:** Timeline analysis and case management
- **Manage:** Endpoint security and administrative controls

### Security Overview Dashboard

Monitor overall security posture and threat landscape from the central dashboard.

![Security Overview Main Dashboard](assets/screenshots/security-overview-main-dashboard.png)

**Dashboard Components:**
- **Recent Cases:** Active security investigations and incidents
- **Detection Alert Trends:** Real-time threat detection metrics
- **External Alert Trends:** Third-party security integration status
- **Security News:** Latest threat intelligence and product updates
- **Event Analysis:** Comprehensive security event distribution

### Alert Management System

Manage and analyze security alerts through the centralized alerts interface.

![Security Alerts Dashboard](assets/screenshots/security-alerts-dashboard.png)

**Alert Management Features:**
- **Alert Trends:** Temporal analysis of security events
- **Risk Scoring:** Severity-based alert prioritization
- **Alert Categories:** Enumeration, persistence, and privilege escalation detection
- **Investigation Workflow:** Direct integration with timeline analysis

### Detection Rules Management

Configure and manage detection rules for automated threat identification.

![Security Rules Management Interface](assets/screenshots/security-rules-management-interface.png)

**Rule Management Capabilities:**
- **Rule Types:** Execution, authentication, and cloud monitoring rules
- **Severity Levels:** High, medium, and low priority classification
- **Rule Status:** Active monitoring and warning state management
- **Custom Rules:** Organization-specific detection logic

---

## Host Security Monitoring

### Host Activity Analysis

Monitor host-level security events and authentication patterns.

![Security Hosts Overview Dashboard](assets/screenshots/security-hosts-overview-dashboard.png)

**Host Monitoring Metrics:**
- **Active Hosts:** 13 monitored systems
- **Authentication Events:** 8,755 successful, 182 failed attempts
- **Unique IP Analysis:** 7,119 source and 7,030 destination addresses
- **Operating System Distribution:** Windows and Linux system monitoring

---

## Network Security Analysis

### Network Overview Dashboard

Analyze network-level security events and traffic patterns.

![Security Network Overview Dashboard](assets/screenshots/security-network-overview-dashboard.png)

**Network Security Insights:**
- **Global Threat Map:** Geographic distribution of security events
- **Network Statistics:** 7.2M events across 12,288 DNS queries
- **IP Address Analysis:** Source and destination traffic patterns
- **Protocol Monitoring:** Comprehensive network protocol analysis

### External Alert Investigation

Investigate external security alerts for advanced threat detection.

![Security Network External Alerts](assets/screenshots/security-network-external-alerts.png)

**External Alert Analysis:**
- **Alert Volume:** 44 external security alerts detected
- **Integration Sources:** Third-party security tool correlation
- **Trend Analysis:** Temporal alert distribution patterns

---

## Practical Threat Investigation

### Cryptominer Detection Case Study

Real-world investigation of cryptocurrency mining malware affecting server performance.

![Cryptominer Domain Detection](assets/screenshots/cryptominer-domain-detection.png)

**Investigation Results:**
- **Malicious Domain:** `cryptominer.lab`
- **Destination IP:** `10.66.66.66`
- **Attack Vector:** Unauthorized cryptocurrency mining operation
- **Impact Assessment:** CPU spikes and performance degradation
- **Investigative Method:** Network alert correlation and domain analysis

**Case Summary:**
An unauthorized user successfully deployed cryptocurrency mining software, causing significant server performance issues. The investigation revealed persistent connections to the malicious domain `cryptominer.lab`, confirming the presence of cryptojacking malware.

---

## SOC Analyst Workflow

### Investigation Methodology

**1. Initial Assessment:**
- Monitor security dashboards for anomalies
- Review alert trends and external notifications
- Identify potential security events requiring investigation

**2. Data Discovery:**
- Use Discover interface for targeted event searches
- Apply appropriate filters and time ranges
- Analyze authentication and network event patterns

**3. Threat Analysis:**
- Correlate events across multiple data sources
- Examine event details and metadata
- Identify indicators of compromise (IOCs)

**4. Incident Response:**
- Document findings and evidence
- Escalate confirmed threats to appropriate teams
- Implement containment and remediation measures

---

## Lab Validation

### Knowledge Check Questions

**Q1:** Which source IP generates the authentication events?  
**A:** `5.188.62.102`

**Q2:** What is the most popular network protocol?  
**A:** DNS

**Q3:** What is the malicious domain that the server keeps connecting to?  
**A:** `cryptominer.lab`

---

## Key Takeaways

### Technical Skills Developed

- **Kibana Navigation:** Mastery of security module interfaces and workflows
- **Data Analysis:** Advanced search techniques and event correlation
- **Threat Detection:** Recognition of authentication anomalies and network threats
- **Investigation Skills:** Systematic approach to security event analysis
- **Dashboard Utilization:** Effective use of security visualization tools

### SOC Operational Benefits

- **Centralized Monitoring:** Unified security event visibility across infrastructure
- **Automated Detection:** Rule-based threat identification and alerting
- **Rapid Investigation:** Streamlined workflows for incident response
- **Threat Intelligence:** Integration of external security data sources
- **Evidence Collection:** Comprehensive logging and forensic capabilities

---

## Next Steps

- [ ] Configure custom detection rules for organization-specific threats
- [ ] Implement advanced Fleet management policies
- [ ] Develop automated response playbooks
- [ ] Integrate additional security data sources
- [ ] Create custom dashboards for specific use cases

---

## Additional Resources

- [Elastic Security Documentation](https://www.elastic.co/guide/en/security/)
- [Kibana User Guide](https://www.elastic.co/guide/en/kibana/)
- [Detection Rules Repository](https://github.com/elastic/detection-rules)

**Lab Completed:** Elastic Security Basics  
**Focus Area:** SOC Operations & Threat Investigation  
**Series Status:** 4 of 5 labs completed
