# Fleet Management & Advanced Policies

## Lab Overview

This advanced lab focuses on enterprise-level Fleet management, covering custom policy creation, integration deployment, and agent management at scale. You'll learn to configure production-ready policies, implement Nginx monitoring integrations, and manage policy assignments across multiple agents in the Comtech enterprise environment.

**Author:** Mykyta Palamarchuk  
**Role Focus:** SOC Analyst | Incident Response Specialist  
**Certification:** CompTIA Security+ (SY0-701)  
**Framework Alignment:** Enterprise Fleet operations and policy management

---

## Learning Objectives

- Master advanced Fleet policy creation and management workflows
- Configure enterprise integrations for production monitoring
- Implement scalable agent policy deployment strategies
- Troubleshoot policy assignments and monitor agent health
- Apply enterprise best practices for Fleet operations
- Develop skills in centralized agent management and automation

## Fleet Architecture & Policy Concepts

### Understanding Agent Policies

Agent policies serve as the cornerstone of Fleet management, defining data collection parameters and integration configurations across your infrastructure. Each policy acts as a centralized configuration template that can be applied to multiple agents, enabling consistent monitoring and security posture across your environment.

**Key Policy Components:**
- **Integration Policies:** Define specific data sources and collection methods
- **Input Configuration:** Specify logs, metrics, and security data streams
- **Agent Settings:** Control resource allocation and operational parameters
- **Deployment Rules:** Govern policy application and update mechanisms

### Policy Management Benefits

- **Centralized Control:** Unified configuration management across all agents
- **Scalable Operations:** Deploy updates to hundreds of agents simultaneously
- **Consistent Monitoring:** Standardized data collection across infrastructure
- **Automated Deployment:** Eliminate manual SSH-based configuration management

---

## Environment Setup

### Kibana Access Configuration

Access the Comtech Fleet management environment through the dedicated Kibana instance.

**Connection Details:**
- **Address:** `elastic.lab`
- **Username:** `elastic`
- **Password:** ***********

**Environment Context:**
- **Organization:** Commensurate Technology (Comtech)
- **Infrastructure:** Web server monitoring and security operations
- **Objective:** Implement enterprise-grade Fleet management

---

## Advanced Policy Creation

### Fleet Policies Interface

Navigate to the Fleet policies management interface to begin creating custom policies.

![Fleet Policies Overview](assets/screenshots/fleet-policies-overview-with-create-button.png)

**Policy Management Features:**
- **Policy Catalog:** View existing policies and their configurations
- **Agent Assignment:** Track which agents use specific policies
- **Integration Count:** Monitor complexity of each policy
- **Creation Workflow:** Streamlined policy development process

### Creating Comtech Enterprise Policy

Develop a custom policy tailored for Comtech's production environment requirements.

![Create Comtech Policy Form](assets/screenshots/create-comtech-policy-form.png)

**Policy Configuration:**
- **Name:** `Comtech policy`
- **Purpose:** Enterprise web server monitoring and security
- **System Monitoring:** Enabled for comprehensive infrastructure visibility
- **Scalability:** Designed for multi-agent deployment

**Configuration Steps:**
1. Navigate to Fleet → Policies → Create agent policy
2. Define policy name as "Comtech policy"
3. Enable system metrics collection
4. Configure advanced options for enterprise requirements
5. Save policy for integration assignment

---

## Integration Management

### Nginx Integration Catalog

Explore the integration catalog to identify monitoring solutions for your infrastructure.

![Nginx Integration Catalog](assets/screenshots/nginx-integration-catalog-overview.png)

**Integration Selection Criteria:**
- **Version Compatibility:** Nginx 0.5.0 experimental features
- **Policy Support:** Verify integration compatibility with custom policies
- **Data Sources:** Logs, metrics, and performance monitoring capabilities
- **Enterprise Features:** Advanced configuration and troubleshooting options

### Nginx Integration Configuration

Configure comprehensive Nginx monitoring for the Comtech web infrastructure.

![Nginx Integration Configuration](assets/screenshots/nginx-integration-configuration-comtech.png)

**Integration Settings:**
- **Integration Name:** `nginx-1`
- **Description:** `Comtech Nginx integration`
- **Policy Assignment:** Comtech policy
- **Agent Enrollment:** 2 agents enrolled with selected policy

### Complete Integration Setup

Finalize Nginx integration with comprehensive monitoring capabilities.

![Nginx Integration Setup Complete](assets/screenshots/nginx-integration-setup-complete.png)

**Advanced Configuration Options:**
- **Log Collection:** Nginx access and error logs
- **Metrics Collection:** Performance and resource utilization
- **REST API Monitoring:** Third-party integration capabilities (experimental)
- **Custom Parameters:** Advanced configuration for enterprise requirements

**Data Stream Configuration:**
- ✅ **Collect logs from Nginx instances**
- ❌ **Collect logs from third-party REST API** (experimental - disabled)
- ✅ **Collect metrics from Nginx instances**

---

## Policy Deployment & Management

### Pre-Deployment Agent Status

Review current agent configuration before implementing the new policy.

![Agents with Default Policies](assets/screenshots/agents-with-default-policies-before.png)

**Current State Analysis:**
- **Agent Count:** 2 active agents
- **Policy Status:** Default policies and Default Fleet Server policy
- **Health Status:** All agents reporting healthy
- **Version:** Elastic Agent 7.13.4

### Policy Assignment Process

Implement the Comtech policy across the agent infrastructure.

![Policy Assignment Process](assets/screenshots/policy-assignment-comtech-integrations.png)

**Assignment Configuration:**
- **Target Policy:** Comtech policy
- **Integration Count:** 2 integrations (System + Nginx)
- **Agent Selection:** All production web servers
- **Deployment Method:** Centralized Fleet management

**Assignment Workflow:**
1. Select agents requiring policy update
2. Choose "Assign to new policy" from bulk actions
3. Select Comtech policy from dropdown
4. Confirm integration compatibility
5. Execute policy assignment

### Post-Deployment Verification

Confirm successful policy deployment and agent health status.

![Fleet Agents Management Overview](assets/screenshots/fleet-agents-management-overview.png)

**Deployment Results:**
- **Policy Status:** Comtech policy rev. 2 active
- **Agent Health:** All agents reporting healthy
- **Last Activity:** Recent check-ins confirmed
- **Integration Status:** System and Nginx monitoring operational

**Verification Metrics:**
- **Response Time:** Policy updates applied within 42-15 seconds
- **Success Rate:** 100% policy deployment success
- **Agent Stability:** No downtime during policy transition

---

## Monitoring & Troubleshooting

### Agent Health Monitoring

**Health Status Indicators:**
- **Green (Healthy):** Agent responsive and collecting data
- **Yellow (Warning):** Minor configuration issues or delays
- **Red (Unhealthy):** Agent offline or critical errors

**Troubleshooting Workflow:**
1. **Policy Validation:** Verify policy syntax and integration compatibility
2. **Agent Logs:** Review Elastic Agent logs for error messages
3. **Network Connectivity:** Confirm Fleet Server communication
4. **Resource Allocation:** Monitor CPU and memory usage during updates

### Performance Optimization

**Best Practices:**
- **Staged Deployment:** Roll out policies to agent subsets
- **Resource Management:** Monitor agent resource consumption
- **Update Scheduling:** Plan policy updates during maintenance windows
- **Rollback Strategy:** Maintain previous policy versions for emergency reversion

---

## Enterprise Best Practices

### Policy Design Principles

**Standardization:**
- Develop organization-wide policy templates
- Implement consistent naming conventions
- Maintain version control for policy changes
- Document integration dependencies

**Scalability:**
- Design policies for horizontal scaling
- Optimize for high-volume data environments
- Implement efficient resource allocation
- Plan for multi-environment deployments

**Security Considerations:**
- Apply least privilege principles to data collection
- Encrypt agent-to-Fleet communication
- Implement access controls for policy management
- Regular security audits of policy configurations

### Automation & DevOps Integration

**Infrastructure as Code:**
- YAML-based policy definitions
- API-driven Fleet management
- CI/CD pipeline integration
- Automated testing and validation

**Monitoring & Alerting:**
- Policy deployment success metrics
- Agent health status monitoring
- Integration performance tracking
- Automated incident response workflows

---

## Lab Validation

### Knowledge Check Questions

**Q1:** What is the name of the custom policy created for Comtech?  
**A:** `Comtech policy`

**Q2:** How many integrations are included in the Comtech policy?  
**A:** 2 integrations (System and Nginx)

**Q3:** What is the integration name assigned to the Nginx monitoring?  
**A:** `nginx-1`

**Q4:** Which data streams are enabled in the Nginx integration?  
**A:** Logs from Nginx instances and Metrics from Nginx instances

---

## Key Takeaways

### Technical Skills Developed

- **Advanced Policy Management:** Custom policy creation and enterprise deployment
- **Integration Configuration:** Nginx monitoring setup with comprehensive data collection
- **Agent Orchestration:** Centralized management of multiple Elastic Agents
- **Troubleshooting Expertise:** Policy deployment validation and health monitoring
- **Enterprise Operations:** Scalable Fleet management workflows

### Operational Benefits

- **Centralized Management:** Unified agent configuration across infrastructure
- **Automated Deployment:** Elimination of manual configuration processes
- **Consistent Monitoring:** Standardized data collection and security posture
- **Rapid Scaling:** Efficient policy deployment to new agents
- **Enhanced Visibility:** Comprehensive monitoring of web infrastructure

### Career Readiness

- **Enterprise Skills:** Production-ready Fleet management capabilities
- **SOC Operations:** Advanced monitoring and incident response preparation
- **DevOps Integration:** Infrastructure as code and automation expertise
- **Troubleshooting:** Systematic approach to agent and policy issues

---

## Next Steps

### Advanced Fleet Operations

- [ ] Implement role-based access controls for policy management
- [ ] Develop custom integration packages for organization-specific requirements
- [ ] Create automated testing frameworks for policy validation
- [ ] Integrate Fleet management with existing ITSM workflows
- [ ] Establish monitoring and alerting for Fleet infrastructure health

### Enterprise Expansion

- [ ] Design multi-environment policy deployment strategies
- [ ] Implement compliance frameworks for data collection policies
- [ ] Develop disaster recovery procedures for Fleet infrastructure
- [ ] Create training materials for operational team members
- [ ] Establish governance processes for policy lifecycle management

---

## Additional Resources

- [Fleet Management Guide](https://www.elastic.co/guide/en/fleet/)
- [Agent Policy Configuration](https://www.elastic.co/guide/en/fleet/current/agent-policy.html)
- [Integration Development](https://www.elastic.co/guide/en/integrations-developer/)
- [API Reference](https://www.elastic.co/guide/en/fleet/current/fleet-api-docs.html)

**Lab Completed:** Fleet Management & Advanced Policies  
**Focus Area:** Enterprise Fleet Operations & Policy Management  
**Series Status:** 5 of 5 labs completed ✅

---

*Congratulations! You have successfully completed the comprehensive Elastic Security Labs series, developing essential skills for SOC operations, threat hunting, and enterprise security management.*
