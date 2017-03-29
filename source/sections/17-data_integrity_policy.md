# 17. Data Integrity Policy

Cloudticity takes data integrity very seriously. As stewards and partners of Cloudticity customers, we strive to assure data is protected from unauthorized access and that it is available when needed. The following policies drive many of our procedures and technical settings in support of the Cloudticity mission of data protection.

Production systems that create, receive, store, or transmit customer data (hereafter "production systems") must follow the guidelines described in this section.

## 17.1 Applicable Standards

### 17.1.1 Applicable Standards from the HITRUST Common Security Framework

* 10.b - Input Data Validation
* 10.g - Key Management

### 17.1.2 Applicable Standards from the HIPAA Security Rule

* 164.308(a)(8) - Evaluation

## 17.2 Disabling Non-Essential Services

1. All production systems must disable services that are not required to achieve the business purpose or function of the system.

## 17.3 Monitoring Log-in Attempts

1. All access to production systems must be logged. This is done following the [Cloudticity Auditing Policy](08-auditing_policy.md).

## 17.4 Prevention of Malware on Production Systems

1. All production systems must have TMDS agents running that monitor systems in real-time to assure malware is not present. Detected malware is evaluated and removed.
2. TMDS is run on all production systems for anti-virus protection.
   * Hosts are scanned daily for malicious binaries in critical system paths.
   * The malware signature database is checked hourly and automatically updated if new signatures are available.
   * Logs of virus scans are maintained according to the requirements outlined in [§8.6](08-auditing_policy.md#86-audit-log-security-controls-and-backup).
3. All production systems are to only be used for Cloudticity business needs.

## 17.5 Patch Management

1. Software patches and updates will be applied to all systems in a timely manner. In the case of routine updates, they will be applied after thorough testing. In the case of updates to correct known vulnerabilities, priority will be given to testing to speed the time to production. Critical security patches are applied within 30 days from testing and all security patches are applied within 90 days after testing.
    * In the case of PaaS customers, updates to application and database versions are the responsibility of customers, though Cloudticity will, at its own discretion, notify and recommend updates to customer systems.
2. Automation is used to ensure monitoring agents are up-to-date on production systems.
3. TMDS implements preventative measures to mitigate potential issues associated with out-of-date software, therefore updating software immediately upon release is unnecessary.

## 17.6 Intrusion Detection and Vulnerability Scanning

1. Production systems are monitored using TMDS for intrusion detection and prevention. Suspicious activity is logged and alerts are generated via Zendesk tickets.
2. Vulnerability scanning of production systems must occur on a predetermined, regular basis, no less than annually. Currently it is daily. When recommendation scans finish, the recommendations are automatically implemented. Due to the automated recommendations, scans are reviewed quarterly by the Security Officer to ensure compliance with this policy. The scans are retained for future reference.

## 17.7 Production System Security

1. System, network, and server security is managed and maintained by a Senior AWS Engineer and the Security Officer.
2. Up to date system lists and architecture diagrams are kept for all production environments.
3. Access to production systems is controlled using centralized tools and two-factor authentication.

## 17.8 Production Data Security

The risk of production data being compromised is reduced by:
1. Controls are implemented and/or reviewed that are designed to protect production data from improper alteration or destruction.
2. Confidential data is stored in a manner that supports user access logs and automated monitoring for potential security incidents.
3. Cloudticity customer production data is segmented and only accessible to personnel authorized to access the data.
4. All production data at rest is stored on encrypted volumes using encryption keys managed by Cloudticity, in conjunction with AWS. Encryption at rest is ensured through the use of automated deployment scripts referenced in the [Cloudticity Configuration Management Policy](09-configuration_management_policy.md).
5. Volume encryption keys and machines that generate volume encryption keys are protected from unauthorized access. Volume encryption key material is protected with access controls such that the key material is only accessible by privileged accounts.
6. Encrypted volumes use AES encryption with a minimum of 256-bit keys, or keys and ciphers of equivalent or higher cryptographic strength.

## 17.9 Transmission Security

1. All data transmission is encrypted end to end using encryption keys managed by Cloudticity, in conjunction with AWS. Encryption may be terminated at the network end point, but is also carried through to the application.
2. Transmission encryption keys and machines that generate keys are protected from unauthorized access. Transmission encryption key material is protected with access controls such that the key material is only accessible by privileged accounts.
3. Transmission encryption keys use a minimum of 2048-bit RSA keys, or keys and ciphers of equivalent or higher cryptographic strength.
4. Transmission encryption keys are limited to use for one year and then must be regenerated.
5. In the case of Cloudticity provided APIs, mechanisms are provided to assure the person sending or receiving data is authorized to send and save data.
6. System logs of all transmissions of production data access are maintained. These logs must be available for audit.
