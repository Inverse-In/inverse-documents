# Logical Security Measures and Control Mechanisms

## 1. Introduction

This document details the logical security measures and mechanisms implemented for each type of external connection to the InversePay system. It specifies the control the applicant will have over these accesses as well as the nature and frequency of each control. The security measures are designed to protect the confidentiality, integrity, and availability of data and systems while ensuring compliance with relevant regulatory requirements.

## 2. Banking Partner Connections

### 2.1 Security Measures and Mechanisms

| Security Measure | Implementation | Control Mechanism | Nature of Control | Frequency |
|-----------------|----------------|-------------------|-------------------|-----------|
| Transport Encryption | TLS 1.3 with Perfect Forward Secrecy | Certificate management system | Technical, automated | Certificates rotated quarterly |
| API Authentication | OAuth 2.0 with JWT | API gateway with token validation | Technical, automated | Tokens expire after 1 hour |
| IP Whitelisting | Firewall rules limiting connections to specific IPs | Network security management console | Technical, manual approval | Reviewed monthly |
| Mutual TLS (mTLS) | Client and server certificate validation | PKI infrastructure | Technical, automated | Certificates rotated quarterly |
| Rate Limiting | API gateway throttling | API management platform | Technical, automated | Continuously enforced, thresholds reviewed quarterly |
| Request Validation | Schema validation, input sanitization | API gateway | Technical, automated | Continuously enforced, rules updated as needed |
| Audit Logging | Comprehensive logging of all transactions | SIEM system | Technical, automated with manual review | Real-time collection, daily review |
| Anomaly Detection | AI-based transaction monitoring | Fraud detection system | Technical, automated with manual investigation | Real-time monitoring, alerts investigated within 15 minutes |

### 2.2 Applicant Control Over Access

| Control Type | Description | Implementation | Authority Level |
|-------------|-------------|----------------|----------------|
| Access Provisioning | Creation of banking partner connections | Multi-level approval workflow | CFO, Head of IT, CISO, CEO approval required |
| Access Modification | Changes to existing connection parameters | Change management process | CFO and CISO approval required |
| Access Revocation | Termination of banking partner access | Emergency and standard revocation procedures | Any C-level executive can initiate emergency revocation |
| Access Review | Periodic validation of connection necessity | Quarterly access review process | CFO and CISO jointly review and certify |
| Parameter Control | Modification of transaction limits, IP whitelist | Self-service portal with approval workflow | Changes require dual approval from Finance and Security |

### 2.3 Control Frequency and Verification

| Control Activity | Frequency | Verification Method | Documentation |
|-----------------|-----------|---------------------|---------------|
| Connection Health Monitoring | Continuous | Automated monitoring system | Availability reports generated daily |
| Security Configuration Review | Monthly | Automated compliance scanning | Compliance reports reviewed by security team |
| Penetration Testing | Quarterly | External security firm testing | Test reports reviewed by CISO |
| Access Recertification | Quarterly | Manual review by system owners | Recertification records maintained for audit |
| Comprehensive Security Audit | Annual | Internal audit team | Audit findings presented to board |
| Regulatory Compliance Assessment | Annual | Compliance team review | Compliance attestation documented |

## 3. Mobile Money Provider Connections

### 3.1 Security Measures and Mechanisms

| Security Measure | Implementation | Control Mechanism | Nature of Control | Frequency |
|-----------------|----------------|-------------------|-------------------|-----------|
| Dedicated Connection | Private MPLS or leased line | Network infrastructure | Technical, physical | Continuous monitoring, annual circuit review |
| API Versioning | Strict API version control | API management platform | Technical, automated | Version compatibility checked on each request |
| Data Encryption | End-to-end encryption | Encryption key management system | Technical, automated | Keys rotated every 90 days |
| Transaction Signing | Digital signatures for all transactions | HSM-based signing service | Technical, automated | Signature verification on every transaction |
| Reconciliation Controls | Automated matching of transactions | Reconciliation system | Technical, automated with manual review | Daily reconciliation, exceptions reviewed within 24 hours |
| Fraud Detection | Rule-based and ML transaction monitoring | Fraud management system | Technical, automated with manual investigation | Real-time monitoring, suspicious transactions reviewed within 30 minutes |
| Segregation of Duties | Different roles for transaction initiation and approval | Identity and access management system | Administrative, enforced technically | Role assignments reviewed quarterly |
| Non-repudiation | Transaction logging with digital signatures | Immutable audit logging | Technical, automated | Continuously enforced, logs retained for 7 years |

### 3.2 Applicant Control Over Access

| Control Type | Description | Implementation | Authority Level |
|-------------|-------------|----------------|----------------|
| Provider Onboarding | Addition of new mobile money providers | Vendor security assessment process | Head of Payments, CISO, CEO approval required |
| Service Configuration | Setting up services, transaction types, limits | Configuration management system | Head of Payments and CISO approval required |
| Emergency Suspension | Ability to suspend connections immediately | Emergency response system | Any director-level employee can initiate, CISO must confirm within 1 hour |
| Transaction Monitoring | Real-time visibility into transaction flows | Monitoring dashboard | Read-only access for authorized personnel |
| Limit Management | Control of transaction and daily limits | Limit management system | Changes require dual approval from Payments and Risk teams |

### 3.3 Control Frequency and Verification

| Control Activity | Frequency | Verification Method | Documentation |
|-----------------|-----------|---------------------|---------------|
| Service Level Monitoring | Continuous | Automated performance monitoring | SLA reports generated daily |
| Transaction Reconciliation | Daily | Automated with manual exception handling | Reconciliation reports maintained for audit |
| Security Incident Simulation | Quarterly | Tabletop exercises with providers | Exercise reports reviewed by security committee |
| Limit Review | Monthly | Risk assessment by treasury team | Limit adjustment recommendations documented |
| Provider Security Assessment | Annual | Security questionnaire and evidence collection | Assessment reports maintained by vendor management |
| Disaster Recovery Testing | Bi-annual | Simulated failover testing | DR test results documented and reviewed |

## 4. International Remittance Partner Connections

### 4.1 Security Measures and Mechanisms

| Security Measure | Implementation | Control Mechanism | Nature of Control | Frequency |
|-----------------|----------------|-------------------|-------------------|-----------|
| Secure API Gateway | Kong API Gateway with security plugins | API management platform | Technical, automated | Configuration reviewed monthly |
| Strong Authentication | API keys + HMAC signatures | Authentication service | Technical, automated | Keys rotated every 60 days |
| Message Encryption | Field-level encryption for sensitive data | Encryption service with HSM | Technical, automated | Encryption keys rotated quarterly |
| Transaction Validation | Multi-step validation with business rules | Rules engine | Technical, automated | Rules reviewed monthly, updated as needed |
| AML Screening | Real-time transaction screening | Sanctions screening system | Technical, automated with manual review | Real-time screening, alerts reviewed within 10 minutes |
| Compliance Controls | Regulatory checks (OFAC, PEP, etc.) | Compliance checking system | Technical, automated with manual review | Real-time checks, daily review of edge cases |
| Audit Trail | Immutable transaction logging | Blockchain-based audit system | Technical, automated | Continuous logging, records retained for 10 years |
| Fraud Monitoring | Behavioral analytics and pattern detection | AI-based fraud system | Technical, automated with manual investigation | Real-time monitoring, alerts investigated within 15 minutes |

### 4.2 Applicant Control Over Access

| Control Type | Description | Implementation | Authority Level |
|-------------|-------------|----------------|----------------|
| Partner Onboarding | Addition of new remittance partners | Enhanced due diligence process | Head of Payments, Compliance Officer, CISO, CEO approval required |
| Corridor Management | Opening/closing specific remittance corridors | Corridor management system | Head of Payments and Compliance Officer approval required |
| Transaction Limits | Setting and adjusting transaction thresholds | Risk-based limit system | Risk Committee approval required for significant changes |
| Compliance Configuration | Tuning of compliance screening parameters | Compliance rule management | Compliance Officer and CISO approval required |
| Emergency Shutdown | Immediate suspension of specific corridors | Emergency control system | Any executive can initiate, Compliance Officer must confirm within 30 minutes |

### 4.3 Control Frequency and Verification

| Control Activity | Frequency | Verification Method | Documentation |
|-----------------|-----------|---------------------|---------------|
| Transaction Monitoring | Continuous | Automated monitoring with risk scoring | Suspicious activity reports generated as needed |
| Compliance Screening Effectiveness | Weekly | False positive/negative analysis | Effectiveness reports reviewed by Compliance Committee |
| Corridor Risk Assessment | Monthly | Risk scoring based on multiple factors | Risk assessment reports maintained for regulatory review |
| Partner Compliance Audit | Quarterly | Remote assessment of partner controls | Audit reports maintained by Compliance team |
| On-site Partner Inspection | Annual | Physical visit to partner operations | Inspection reports reviewed by executive team |
| Regulatory Examination | Annual | Regulatory authority review | Examination findings addressed within specified timeframes |

## 5. Technical Service Provider Connections

### 5.1 Security Measures and Mechanisms

| Security Measure | Implementation | Control Mechanism | Nature of Control | Frequency |
|-----------------|----------------|-------------------|-------------------|-----------|
| Identity Federation | SAML/OAuth-based SSO | Identity provider | Technical, automated | Federation metadata reviewed quarterly |
| Privileged Access Management | Just-in-time access provisioning | PAM solution | Technical, automated with approval workflow | Access requests reviewed in real-time |
| Network Segmentation | Micro-segmentation for provider access | Software-defined networking | Technical, automated | Segmentation rules reviewed quarterly |
| Data Loss Prevention | Content inspection for sensitive data | DLP solution | Technical, automated with alerts | Real-time monitoring, policies reviewed monthly |
| Secure API Integration | API gateway with security controls | API management platform | Technical, automated | Security configurations reviewed monthly |
| Third-party Access VPN | Dedicated VPN for service providers | VPN concentrator with MFA | Technical, automated | Connection logs reviewed daily |
| Session Recording | Video recording of privileged sessions | Session recording solution | Technical, automated | High-risk sessions reviewed within 24 hours |
| Vendor Access Portal | Dedicated portal for vendor access | Access management system | Technical, automated with approval workflow | Portal security reviewed quarterly |

### 5.2 Applicant Control Over Access

| Control Type | Description | Implementation | Authority Level |
|-------------|-------------|----------------|----------------|
| Vendor Onboarding | Addition of new technical service providers | Security assessment process | CTO and CISO approval required |
| Access Scope Definition | Defining allowed systems and data access | Access matrix management | System owner and CISO approval required |
| Access Scheduling | Time-bound access windows | Scheduled access control system | System owner can approve standard windows, CISO required for exceptions |
| Emergency Access | Break-glass procedure for urgent access | Emergency access system | CTO or CISO approval required, all access logged and reviewed |
| Access Termination | Immediate revocation of vendor access | Centralized access control | Any manager can initiate, automatically executed |

### 5.3 Control Frequency and Verification

| Control Activity | Frequency | Verification Method | Documentation |
|-----------------|-----------|---------------------|---------------|
| Access Log Review | Daily | Automated log analysis with manual review | Access reports reviewed by security team |
| Vendor Access Recertification | Monthly | System owners verify continued need | Recertification records maintained for audit |
| Vendor Security Reassessment | Quarterly | Automated security posture checking | Security posture reports reviewed by CISO |
| Penetration Testing of Vendor Access | Bi-annual | External security firm testing | Test reports reviewed by security team |
| Comprehensive Vendor Security Review | Annual | In-depth security assessment | Assessment reports maintained by vendor management |
| Vendor Compliance Verification | Annual | Compliance attestation collection | Compliance documentation maintained for audit |

## 6. Operational Service Provider Connections

### 6.1 Security Measures and Mechanisms

| Security Measure | Implementation | Control Mechanism | Nature of Control | Frequency |
|-----------------|----------------|-------------------|-------------------|-----------|
| Data Minimization | Tokenization of sensitive data | Tokenization service | Technical, automated | Token mappings reviewed quarterly |
| Purpose-Based Access | Context-aware access controls | Attribute-based access control system | Technical, automated | Access policies reviewed monthly |
| Secure File Transfer | SFTP with PGP encryption | Managed file transfer solution | Technical, automated | Transfer logs reviewed daily |
| Data Classification | Automated data classification | DLP with classification engine | Technical, automated with manual verification | Classification rules reviewed quarterly |
| Access Monitoring | User and entity behavior analytics | UEBA platform | Technical, automated with alerts | Continuous monitoring, alerts investigated within 30 minutes |
| Data Masking | Dynamic data masking for non-production | Data masking solution | Technical, automated | Masking rules reviewed quarterly |
| API Security Gateway | API security with data filtering | API gateway | Technical, automated | Security policies reviewed monthly |
| Secure Data Exchange | Encrypted data exchange protocols | Encryption gateway | Technical, automated | Encryption configurations reviewed quarterly |

### 6.2 Applicant Control Over Access

| Control Type | Description | Implementation | Authority Level |
|-------------|-------------|----------------|----------------|
| Provider Onboarding | Addition of new operational service providers | Vendor risk assessment process | Department Head and CISO approval required |
| Data Access Scope | Definition of accessible data elements | Data access matrix | Data owner and CISO approval required |
| Processing Limitations | Controls on data usage and processing | Data processing agreement enforcement | Legal and Compliance approval required |
| Audit Rights | Right to audit provider security controls | Contractual audit provisions | Audit can be initiated by CISO or Compliance Officer |
| Service Termination | Controlled disconnection and data return | Offboarding process | Department Head can initiate, CISO oversees data return |

### 6.3 Control Frequency and Verification

| Control Activity | Frequency | Verification Method | Documentation |
|-----------------|-----------|---------------------|---------------|
| Data Transfer Monitoring | Continuous | Automated monitoring of data flows | Data transfer logs retained for 2 years |
| Data Usage Audit | Monthly | Sampling of data access and usage | Usage audit reports reviewed by data owners |
| Privacy Impact Assessment | Quarterly | Review of privacy implications | PIA reports maintained by Privacy Officer |
| Provider Compliance Verification | Bi-annual | Compliance attestation and evidence collection | Compliance documentation maintained by vendor management |
| Data Protection Audit | Annual | Comprehensive audit of data protection controls | Audit reports reviewed by executive team |
| Contract Compliance Review | Annual | Review of contractual obligations | Compliance reports maintained by Legal team |

## 7. Group Entity Connections

### 7.1 Security Measures and Mechanisms

| Security Measure | Implementation | Control Mechanism | Nature of Control | Frequency |
|-----------------|----------------|-------------------|-------------------|-----------|
| Secure Inter-entity Network | MPLS or SD-WAN with encryption | Network infrastructure | Technical, automated | Network security reviewed quarterly |
| Cross-entity Authentication | Federated identity with SSO | Enterprise identity provider | Technical, automated | Federation trust reviewed quarterly |
| Data Governance Controls | Centralized data governance framework | Data governance platform | Technical and administrative | Governance rules reviewed monthly |
| Shared Service Security | Micro-segmentation for shared services | Zero-trust network architecture | Technical, automated | Segmentation rules reviewed quarterly |
| Cross-entity Data Transfer | Secure ETL processes with encryption | Data integration platform | Technical, automated | Transfer processes reviewed monthly |
| Group-wide Monitoring | Centralized security monitoring | Enterprise SIEM | Technical, automated with manual review | Continuous monitoring, cross-entity alerts reviewed daily |
| Regulatory Boundary Controls | Controls for cross-border data transfers | Data transfer gateway | Technical, automated with compliance checks | Transfer rules reviewed monthly |
| Group Policy Enforcement | Automated policy compliance checking | Policy compliance platform | Technical, automated with exceptions workflow | Policy compliance reviewed monthly |

### 7.2 Applicant Control Over Access

| Control Type | Description | Implementation | Authority Level |
|-------------|-------------|----------------|----------------|
| Entity Access Authorization | Approval of cross-entity access | Multi-entity approval workflow | Department Head and entity CISO approval required |
| Data Sharing Agreements | Formal agreements for data sharing | Data sharing framework | Legal, Compliance, and executive approval required |
| Shared Service Management | Control of shared service access | Centralized service management | Service owner and Group CISO approval required |
| Cross-entity Integration | New integrations between entities | Integration approval process | CTO, CISO, and entity heads approval required |
| Group-wide Policy Exceptions | Exceptions to group security policies | Exception management system | Group CISO and entity CISO approval required |

### 7.3 Control Frequency and Verification

| Control Activity | Frequency | Verification Method | Documentation |
|-----------------|-----------|---------------------|---------------|
| Cross-entity Access Review | Monthly | Automated access review with manual verification | Access review reports maintained for audit |
| Data Sharing Compliance | Quarterly | Audit of data sharing practices | Compliance reports reviewed by Group Compliance |
| Shared Service Security Assessment | Quarterly | Security testing of shared services | Assessment reports reviewed by Group CISO |
| Cross-entity Security Testing | Bi-annual | Penetration testing across entity boundaries | Test reports reviewed by Group Security Committee |
| Group Security Posture Assessment | Annual | Comprehensive security assessment | Assessment reports presented to Group Board |
| Regulatory Compliance Verification | Annual | Multi-jurisdiction compliance review | Compliance documentation maintained for regulatory review |

## 8. Remote Employee Connections

### 8.1 Security Measures and Mechanisms

| Security Measure | Implementation | Control Mechanism | Nature of Control | Frequency |
|-----------------|----------------|-------------------|-------------------|-----------|
| Secure Remote Access | VPN with split tunneling | VPN infrastructure | Technical, automated | Connection logs reviewed daily |
| Device Authentication | Certificate-based device authentication | PKI infrastructure | Technical, automated | Device certificates rotated annually |
| Multi-factor Authentication | Hardware tokens or mobile app MFA | Identity provider with MFA | Technical, automated | MFA enrollment verified quarterly |
| Endpoint Security | Advanced endpoint protection | EDR solution | Technical, automated | Endpoint security posture checked continuously |
| Network Access Control | Posture assessment before connection | NAC solution | Technical, automated | Posture requirements reviewed monthly |
| Data Loss Prevention | Endpoint DLP controls | DLP client | Technical, automated | DLP policies reviewed quarterly |
| Session Controls | Automatic timeout and session monitoring | Remote access gateway | Technical, automated | Session parameters reviewed quarterly |
| Remote Wipe Capability | Remote device management | MDM solution | Technical, automated | Wipe capability tested quarterly |

### 8.2 Applicant Control Over Access

| Control Type | Description | Implementation | Authority Level |
|-------------|-------------|----------------|----------------|
| Remote Access Authorization | Approval of remote work capability | Remote work approval workflow | Department Head approval required |
| Access Level Definition | Setting appropriate access levels | Role-based access control | Department Head and Security Manager approval required |
| Geographic Restrictions | Limiting access from specific regions | Geolocation-based access control | Security Manager can configure, CISO approval for exceptions |
| Device Authorization | Approval of devices for remote access | Device enrollment process | IT Manager approval required |
| Emergency Access Revocation | Immediate termination of remote access | Emergency revocation system | Any manager can initiate, automatically executed |

### 8.3 Control Frequency and Verification

| Control Activity | Frequency | Verification Method | Documentation |
|-----------------|-----------|---------------------|---------------|
| Remote Connection Monitoring | Continuous | Automated monitoring with anomaly detection | Connection logs retained for 1 year |
| Device Compliance Checking | Daily | Automated compliance verification | Compliance reports reviewed by IT Security |
| Remote Access Recertification | Monthly | Manager verification of continued need | Recertification records maintained for audit |
| Security Awareness Verification | Quarterly | Security knowledge testing | Training completion records maintained by HR |
| Remote Security Assessment | Bi-annual | Security testing of remote access infrastructure | Assessment reports reviewed by CISO |
| Remote Work Policy Review | Annual | Comprehensive policy review | Policy updates communicated to all employees |

## 9. Regulatory and Compliance Connections

### 9.1 Security Measures and Mechanisms

| Security Measure | Implementation | Control Mechanism | Nature of Control | Frequency |
|-----------------|----------------|-------------------|-------------------|-----------|
| Dedicated Regulatory Connection | Leased lines or encrypted VPN | Network infrastructure | Technical, physical | Circuit security reviewed quarterly |
| Secure File Transfer | SFTP with PGP encryption | Managed file transfer solution | Technical, automated | Transfer logs reviewed daily |
| Data Integrity Controls | Digital signatures and checksums | Cryptographic service | Technical, automated | Signature verification on every transfer |
| Non-repudiation | Transaction signing with timestamps | HSM-based signing service | Technical, automated | Signature logs retained for 10 years |
| Regulatory Portal Access | Dedicated secure browser environment | Secure access workstations | Technical, physical | Access logs reviewed daily |
| Submission Validation | Multi-level validation before submission | Validation engine | Technical, automated with manual review | Validation rules reviewed monthly |
| Regulatory Data Warehouse | Segregated data storage for regulatory data | Dedicated database infrastructure | Technical, physical | Access controls reviewed monthly |
| Audit Trail | Comprehensive logging of all regulatory interactions | Immutable audit logging | Technical, automated | Logs retained according to regulatory requirements |

### 9.2 Applicant Control Over Access

| Control Type | Description | Implementation | Authority Level |
|-------------|-------------|----------------|----------------|
| Regulatory Reporting Authorization | Approval of regulatory reporting access | Formal authorization process | Compliance Officer, CISO, CEO approval required |
| Submission Approval | Multi-level approval for regulatory submissions | Workflow approval system | Compliance Officer and CFO approval required for financial reports |
| Regulatory Data Access | Control of access to regulatory data | Privileged access management | Compliance Officer approval required |
| Reporting Schedule Management | Control of reporting schedules and deadlines | Regulatory calendar system | Compliance Officer manages schedule |
| Regulatory Communication | Management of formal communications | Communication management system | Compliance Officer and Legal approval required |

### 9.3 Control Frequency and Verification

| Control Activity | Frequency | Verification Method | Documentation |
|-----------------|-----------|---------------------|---------------|
| Submission Accuracy Verification | Per submission | Multi-level review and validation | Verification records maintained for each submission |
| Regulatory Portal Security Review | Monthly | Security assessment of portal access | Security review reports maintained by Compliance |
| Reporting Completeness Check | Quarterly | Audit of regulatory reporting obligations | Completeness reports reviewed by Compliance Committee |
| Regulatory Data Access Audit | Quarterly | Review of access to regulatory data | Access audit reports maintained for regulatory review |
| Mock Regulatory Examination | Annual | Simulation of regulatory examination | Exercise reports reviewed by executive team |
| Regulatory Reporting Framework Audit | Annual | Comprehensive audit of reporting controls | Audit reports presented to board Risk Committee |

## 10. Conclusion and Security Control Integration

### 10.1 Integrated Security Control Framework

The logical security measures described in this document are implemented within an integrated security control framework that ensures consistent protection across all connection types. This framework includes:

1. **Centralized Identity and Access Management**
   * Single source of truth for all identities
   * Consistent authentication and authorization policies
   * Automated access provisioning and deprovisioning
   * Regular access reviews and recertification

2. **Unified Security Monitoring**
   * Centralized SIEM for all connection types
   * Correlation of events across different connection types
   * Holistic threat detection and response
   * Integrated security dashboard for all connections

3. **Standardized Security Controls**
   * Consistent encryption standards across all connections
   * Uniform logging and audit requirements
   * Standardized security testing methodologies
   * Common security incident response procedures

4. **Comprehensive Risk Management**
   * Regular risk assessments for all connection types
   * Consistent risk acceptance and mitigation processes
   * Integrated risk reporting to executive management
   * Continuous improvement based on risk findings

### 10.2 Control Effectiveness Measurement

The effectiveness of the logical security measures is regularly assessed through:

| Assessment Method | Frequency | Scope | Responsibility |
|-------------------|-----------|-------|---------------|
| Security Metrics Dashboard | Real-time | All connection types | Security Operations |
| Control Effectiveness Testing | Monthly | Sample of controls across connection types | Security Testing Team |
| Independent Security Assessment | Quarterly | Rotating focus on different connection types | External Security Firm |
| Comprehensive Security Audit | Annual | All connection types and controls | Internal Audit |
| Regulatory Examination | Annual | Compliance with regulatory requirements | Regulatory Authorities |

### 10.3 Continuous Improvement Process

The logical security measures are subject to continuous improvement through:

1. **Regular Review Cycle**
   * Monthly security control reviews
   * Quarterly security strategy updates
   * Annual comprehensive security framework assessment

2. **Threat Intelligence Integration**
   * Continuous monitoring of emerging threats
   * Regular updates to security controls based on threat intelligence
   * Proactive security posture adjustments

3. **Incident-Driven Improvements**
   * Post-incident reviews and lessons learned
   * Security control enhancements based on incident findings
   * Regular security incident simulations

4. **Technology Evolution**
   * Regular assessment of security technology landscape
   * Planned upgrades to security infrastructure
   * Adoption of emerging security technologies

This document provides a comprehensive overview of the logical security measures and control mechanisms implemented for each type of external connection to the InversePay system. These measures ensure the confidentiality, integrity, and availability of data and systems while providing appropriate levels of control and oversight to the applicant.
