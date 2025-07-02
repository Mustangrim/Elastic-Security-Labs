# Elastic Agent: Installation on Windows

## Lab Overview

This hands-on lab demonstrates deploying Elastic Agent on Windows workstations using an existing Fleet infrastructure. You'll learn Windows-specific installation procedures, PowerShell deployment, and agent policy management - critical skills for enterprise endpoint monitoring and security operations.

**Author:** Mykyta Palamarchuk  
**Role Focus:** SOC Analyst | Incident Response Specialist  
**Certification:** CompTIA Security+ (SY0-701)  
**Framework Alignment:** Windows endpoint security and centralized monitoring

---

## Learning Objectives

- Deploy Elastic Agent on Windows systems using Fleet enrollment
- Master PowerShell-based agent installation procedures
- Understand Windows endpoint monitoring capabilities
- Configure agent policies for workstation environments
- Implement Elastic Defend integration for endpoint security

## Architecture Overview

### Fleet Server Communication Flow

Fleet Server provides centralized management for all Elastic Agents, enabling policy distribution and status monitoring across mixed OS environments.

![Fleet Architecture Diagram](assets/screenshots/fleet-architecture-diagram.png)

**Communication Workflow:**
1. **Policy Storage:** Agent policies stored in Elasticsearch
2. **Enrollment:** Agents authenticate using enrollment tokens
3. **Policy Distribution:** Fleet Server delivers policies to enrolled agents
4. **Data Collection:** Agents collect and forward data per policy configuration
5. **Status Monitoring:** Fleet Server tracks agent health and activity

---

## Agent Deployment Process

### Step 1: Agent Policy Selection

Choose appropriate policy for Windows workstation monitoring.

![Windows Agent Policy Selection](assets/screenshots/windows-agent-policy-selection.png)

**Default Agent Policy includes:**
- **System Integration:** OS metrics and logs collection
- **Elastic Defend:** Endpoint security and threat detection

**Policy Benefits:**
- Pre-configured data collection rules
- Automatic security monitoring
- Standardized endpoint visibility

### Step 2: Fleet Enrollment Mode

Select Fleet mode for centralized management capabilities.

![Fleet Enrollment Options](assets/screenshots/fleet-enrollment-options.png)

**Fleet vs Standalone:**
- **Fleet Mode (Recommended):** Centralized policy management and updates
- **Standalone Mode:** Manual configuration and local management

**Fleet Advantages:**
- Automatic policy updates
- Centralized monitoring
- Simplified scaling

### Step 3: Windows Platform Configuration

Configure installation parameters for Windows environment.

![Windows Platform Selection](assets/screenshots/windows-platform-selection.png)

**Installation Components:**
- Platform-specific agent binary
- PowerShell installation commands
- Fleet Server enrollment URL
- Authentication credentials

---

## PowerShell Installation

### Execute Installation Command

Run the provided PowerShell command with administrative privileges.

![PowerShell Agent Installation](assets/screenshots/powershell-agent-installation.png)

**Installation Process:**
1. **Download:** Agent binary retrieved from Elastic artifacts
2. **Archive Extraction:** Agent files extracted to destination
3. **Service Installation:** Agent installed as Windows service
4. **Fleet Enrollment:** Agent registers with Fleet Server
5. **Service Start:** Monitoring and data collection begins

**PowerShell Requirements:**
- Administrator privileges required
- Internet connectivity for download
- Fleet Server connectivity (port 8220)

---

## Enrollment Verification

### Confirm Successful Registration

Verify agent enrollment and policy assignment in Fleet dashboard.

![Windows Agent Enrollment Confirmation](assets/screenshots/windows-agent-enrollment-confirmation.png)

**Verification Indicators:**
- **Agent Status:** "Healthy" indicates successful enrollment
- **Policy Assignment:** Confirms Default Agent Policy application
- **Last Activity:** Shows recent communication with Fleet Server

**Troubleshooting:**
- Check Windows Firewall settings
- Verify Fleet Server connectivity
- Review Windows Event Logs for errors

---

## Policy Integration Analysis

### Default Agent Policy Components

Review integrations and monitoring capabilities enabled by default policy.

![Agent Policy Integrations View](assets/screenshots/agent-policy-integrations-view.png)

**Active Integrations:**

**System Integration (v1.20.4):**
- Windows Event Logs collection
- System performance metrics
- Process and service monitoring
- Network connection tracking

**Elastic Defend (v8.5.0):**
- Real-time threat detection
- Malware protection
- Behavioral analysis
- Endpoint response capabilities

---

## Security Monitoring Capabilities

### Windows Endpoint Protection

**Threat Detection:**
- Malware identification and quarantine
- Suspicious process behavior analysis
- Network anomaly detection
- File integrity monitoring

**Compliance Monitoring:**
- Security policy enforcement
- Configuration drift detection
- Patch level assessment
- User activity tracking

**Incident Response:**
- Real-time alert generation
- Forensic data collection
- Remote response actions
- Timeline reconstruction

---

## SOC Integration Benefits

### Centralized Visibility

**Operational Advantages:**
- **Unified Dashboard:** Single pane for all Windows endpoints
- **Policy Consistency:** Standardized monitoring across workstations
- **Automatic Updates:** Fleet-managed agent and policy updates
- **Scale Efficiency:** Simplified deployment for large environments

**Security Enhancements:**
- **Real-time Monitoring:** Continuous endpoint surveillance
- **Threat Correlation:** Cross-endpoint attack pattern detection
- **Response Automation:** Automated containment and remediation
- **Compliance Reporting:** Automated security posture assessment

---

## Lab Validation

### Knowledge Check

**Q:** What integration besides System has been added to the Default Agent Policy?  
**A:** Elastic Defend

**Q:** Which PowerShell execution policy setting is recommended for agent installation?  
**A:** Run PowerShell as Administrator

**Q:** What port does Fleet Server use for agent communication?  
**A:** 8220

---

## Key Takeaways

### Technical Skills Developed:

- **Windows Deployment:** PowerShell-based agent installation procedures
- **Fleet Management:** Centralized agent enrollment and policy assignment
- **Endpoint Security:** Elastic Defend configuration and monitoring
- **Policy Management:** Understanding integration capabilities and configuration

### Enterprise Implementation:

- **Scalability:** Simplified deployment across Windows infrastructure
- **Security:** Enhanced endpoint protection and monitoring
- **Management:** Centralized policy control and agent lifecycle
- **Compliance:** Automated security monitoring and reporting

---

## Next Steps

- [ ] Explore custom agent policy creation for specific use cases
- [ ] Configure advanced Elastic Defend detection rules
- [ ] Implement Fleet server high availability
- [ ] Set up automated agent deployment via Group Policy
- [ ] Configure integration with Windows Active Directory

---

## Additional Resources

- [Elastic Agent on Windows Documentation](https://www.elastic.co/guide/en/fleet/current/install-fleet-managed-elastic-agent.html)
- [Elastic Defend Integration Guide](https://www.elastic.co/guide/en/security/current/install-endpoint.html)
- [PowerShell Deployment Best Practices](https://www.elastic.co/guide/en/fleet/current/elastic-agent-installation.html)

**Lab Completed:** Elastic Agent Installation on Windows  
**Focus Area:** Windows Endpoint Monitoring & Fleet Management  
**Next Lab:** Elastic Security Basics
