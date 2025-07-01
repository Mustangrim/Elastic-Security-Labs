# Elastic Agent: Installation on Linux

## Lab Overview

This hands-on lab demonstrates the complete process of deploying Elastic Agent on Linux systems using Fleet management. You'll configure X-Pack security, set up Fleet Server, and establish centralized agent management - essential skills for SOC operations and enterprise security monitoring.

**Author:** Mykyta Palamarchuk  
**Role Focus:** SOC Analyst | Incident Response Specialist  
**Certification:** CompTIA Security+ (SY0-701)  
**Framework Alignment:** Enterprise SIEM deployment and agent management

---

## Learning Objectives

- Configure X-Pack security for Elasticsearch and Kibana
- Set up Fleet Server for centralized agent management
- Deploy Elastic Agent in Fleet mode on Linux systems
- Understand agent policies and service token authentication
- Master Fleet management workflows for SOC operations

## Architecture Overview

### Fleet Management Architecture

Fleet provides centralized management for Elastic Agents across your infrastructure, enabling policy distribution, status monitoring, and coordinated data collection.

![Fleet Architecture Diagram](assets/screenshots/fleet-architecture-diagram.png)

**Key Components:**
- **Elastic Agents:** Collect data from endpoints
- **Fleet Server:** Centralized management and policy distribution
- **Elasticsearch:** Data storage and policy persistence
- **Kibana Fleet UI:** Management interface and monitoring

---

## Security Configuration

### Step 1: Configure Elasticsearch Security

Enable X-Pack security features to secure your Elastic Stack deployment.

#### Required Configuration (elasticsearch.yml):

![Elasticsearch Security Configuration](assets/screenshots/elasticsearch-security-config.png)

**Key Settings:**
```yaml
xpack.security.enabled: true
xpack.security.authc.api_key.enabled: true
```

**Security Features Enabled:**
- User authentication and authorization
- API key management for agent communication
- Role-based access control (RBAC)

#### Generate Built-in User Passwords:

![Generated Passwords Output](assets/screenshots/generated-passwords-output.png)

**Critical Users:**
- **elastic:** Superuser for administrative tasks
- **kibana_system:** Kibana service account
- **logstash_system:** Logstash integration
- **beats_system:** Legacy beats authentication

### Step 2: Configure Kibana Security

Update Kibana configuration to integrate with secured Elasticsearch.

![Kibana Security Configuration](assets/screenshots/kibana-security-configuration.png)

**Required Settings:**
```yaml
xpack.encryptedSavedObjects.encryptionKey: "a_secure_key_with_32_characters_or_more"
xpack.security.enabled: true
elasticsearch.username: "kibana_system"
elasticsearch.password: ""
```

---

## Fleet Server Setup

### Configure Fleet Settings

Set up global Fleet configuration for agent management and communication.

![Fleet Server Settings](assets/screenshots/fleet-server-settings-configuration.png)

**Configuration Requirements:**
- **Fleet Server Host:** `http://elastic.lab:8220`
- **Elasticsearch Host:** `http://elastic.lab:9200`

**Fleet Capabilities:**
- Centralized policy management
- Agent health monitoring
- Bulk configuration updates
- Integration deployment

---

## Elastic Agent Installation

### Generate Service Token

Create authentication token for Fleet Server enrollment.

![Service Token Generation](assets/screenshots/fleet-service-token-generation.png)

**Token Purpose:**
- Authenticates Fleet Server with Elasticsearch
- Grants permissions for policy management
- Enables secure agent enrollment

### Install Agent on Linux

Execute installation command with Fleet enrollment:

![Agent Installation Process](assets/screenshots/elastic-agent-installation-output.png)

**Installation Command:**
```bash
sudo ./elastic-agent install -f \
  --fleet-server-es=http://elastic.lab:9200 \
  --fleet-server-service-token=
```

**Installation Process:**
1. Downloads and installs Fleet Server component
2. Generates self-signed certificates
3. Establishes connection with Elasticsearch
4. Enrolls agent in default policy
5. Starts data collection services

---

## Fleet Management

### Agent Dashboard

Monitor and manage deployed agents through the Fleet interface.

![Fleet Agents Dashboard](assets/screenshots/fleet-agents-dashboard.png)

**Dashboard Features:**
- **Agent Status:** Real-time health monitoring
- **Policy Assignment:** Current agent policy configuration
- **Version Tracking:** Agent software versions
- **Activity Logs:** Recent agent communications

**Default Agent Policy:**
- System metrics collection
- Log file monitoring
- Security event detection
- Performance monitoring

---

## SOC Integration Points

### Security Operations Use Cases

**Real-time Monitoring:**
- Endpoint activity tracking
- System performance metrics
- Security event correlation
- Threat detection alerts

**Incident Response:**
- Centralized log analysis
- Timeline reconstruction
- Evidence collection
- Forensic data gathering

**Compliance Management:**
- Audit trail maintenance
- Policy enforcement
- Configuration monitoring
- Reporting automation

---

## Lab Validation

### Knowledge Check

**Q:** Which policy is assigned to the agent after installation?  
**A:** Default Fleet Server policy

**Q:** What port does Fleet Server use for communication?  
**A:** 8220

**Q:** Which authentication method is used for agent enrollment?  
**A:** Service token

---

## Key Takeaways

### Technical Skills Developed:

- **Security Configuration:** X-Pack setup and user management
- **Fleet Management:** Centralized agent deployment and monitoring
- **Linux Administration:** Service configuration and troubleshooting
- **Enterprise Architecture:** Understanding SIEM agent infrastructure

### SOC Operational Benefits:

- **Scalability:** Simplified multi-host monitoring deployment
- **Security:** Encrypted communication and role-based access
- **Efficiency:** Automated policy distribution and updates
- **Visibility:** Centralized agent health and performance monitoring

---

## 🔧 Next Steps

- [ ] Configure custom agent policies for specific use cases
- [ ] Set up Windows agent deployment
- [ ] Implement security integrations and detection rules
- [ ] Explore advanced Fleet management features
- [ ] Configure data retention and index lifecycle management

---

## Additional Resources

- [Elastic Agent Documentation](https://www.elastic.co/guide/en/fleet/)
- [Fleet Management Guide](https://www.elastic.co/guide/en/kibana/current/fleet.html)
- [X-Pack Security Features](https://www.elastic.co/guide/en/elasticsearch/reference/current/security-getting-started.html)

**Lab Completed:** Elastic Agent Installation on Linux  
**Focus Area:** Fleet Management & Security Configuration  
**Next Lab:** Elastic Agent Installation on Windows
