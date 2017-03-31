# 1. Introduction

Cloudticity, LLC. ("Cloudticity") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its customers. As providers of compliant, hosted infrastructure used by health technology vendors, developers, designers, agencies, custom development shops, and enterprises, Cloudticity strives to maintain compliance, proactively address information security, mitigate risk for its customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by Cloudticity to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for Cloudticity customers.

Cloudticity provides secure and compliant cloud-based software. This hosted software falls into two broad categories: 1) **Platform as a Service (PaaS)** and 2) **Platform Add-ons**. These categories are cited throughout Cloudticity's polices, as customers in each category inherit different policies, procedures, and obligations from Cloudticity.

## 1.1 Platform as a Service (PaaS)

PaaS customers utilize hosted software and infrastructure through Cloudticity to deploy, host, and scale custom developed applications and configured databases. These customers are deployed onto compliant resources run on systems secured and managed by Cloudticity. Cloudticity does not have insight into application level data of PaaS customers and, as such, does not have the ability to secure or manage risk associated with application level vulnerabilities and security weaknesses. Cloudticity makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of PaaS customer data through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, TMDS throughout the platform, etc).

PaaS customers can opt for a list of services from Cloudticity, which include custom development, backup creation/removal, IDS/IPS, and disaster recovery. Some of these services are not standard and PaaS customers must sign up for them in order for Cloudticity to manage these areas of security and compliance.

## 1.2 Platform Add-ons

Add-ons are compliant services that are offered as part of the Cloudticity Oxygen platform. These services currently include Monitoring as a Service (MaaS) and Security as a Service (SaaS). With add-ons, Cloudticity has access to data models and manages all application level configurations and security.

In the future there may be 3rd party add-on services available as part of the Cloudticity Oxygen managed services platform. These 3rd party, or Partner, services will be fully reviewed by Cloudticity to assure they do not have a negative impact on Cloudticity's information security and compliance posture.

## 1.3 Compliance Inheritance

Cloudticity provides compliant hosted software infrastructure for its customers. Cloudticity is going through a HIPAA compliance audit by a national, 3rd party compliance firm, to validate and map organizational policies and technical settings to HIPAA rules.

Cloudticity signs business associate agreements (BAAs) with its customers. These BAAs outline Cloudticity obligations and customer obligations, as well as liability in the case of a breach. In providing infrastructure and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, Cloudticity manages various aspects of compliance for customers. The aspects of compliance that Cloudticity manages for customers are inherited by customers, and Cloudticity assumes the risk associated with those aspects of compliance. In doing so, Cloudticity helps customers achieve and maintain compliance, as well as mitigate risk.

Cloudticity does not act as a covered entity. When Cloudticity does operate as a business associate (not a subcontractor), Cloudticity does not interface with users to obtain or provide access to ePHI. Access to ePHI is handled through our customers' applications.

Certain aspects of compliance cannot be inherited. Because of this, Cloudticity customers, in order to achieve full compliance or HITRUST Certification, must implement certain organizational policies. These policies and aspects of compliance fall outside of the services and obligations of Cloudticity.

Mappings of HIPAA Rules to Cloudticity controls and a mapping of what rules are inherited by customers, both Platform customers and Add-on customers, are covered in [§2](02-hipaa_inheritance.md).

## 1.4 Cloudticity Organizational Concepts

The physical infrastructure environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS). The network components and supporting network infrastructure are contained within the AWS infrastructures and managed by AWS. Cloudticity does not have physical access into the network components. The Cloudticity environment consists of OpenVPN firewalls, Wordpress web servers, SQL Server database servers, Chef configuration management servers, Trend Micro IDS/IPS servers, and developer tool servers running on Linux and Windows Server virtual machines.

Within the Cloudticity Oxygen managed services platform on AWS, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting databases, APIs, log servers, etc. Cloudticity assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

In the case of PaaS customers, it is the responsibility of the customer to restrict, secure, and assure the privacy of all ePHI data at the application level, as this is not under the control or purview of Cloudticity.

The data and network segmentation mechanism differs depending on the primitives offered by the underlying cloud provider infrastructure:

* Within AWS, hosted load balancers segment data across dedicated Virtual Private Clouds for PaaS customers and for Platform Add-ons.

The result of segmentation strategies employed by Cloudticity effectively create RFC 1918, or dedicated, private segmented and separated networks and IP spaces, for each PaaS customer and for Platform Add-ons.

Additionally, security groups are used on each server for logical segmentation. Security groups are configured to restrict access to only justified ports and protocols. Cloudticity has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over an SSL encrypted session.

The OpenVPN appliance and Wordpress web servers are externally facing and accessible via the Internet. The database servers, where potential ePHI resides, are located on the internal Cloudticity network and can only be accessed directly over an SSH connection through the OpenVPN appliance. Access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business justified reason. Remote access to the internal servers is not accessible except through the load balancers and OpenVPN.

All platform add-ons and operating systems are tested end-to-end for usability, security, and impact prior to deployment to production.

## 1.5 Requesting Audit and Compliance Reports

Cloudticity, at its sole discretion, shares audit reports, including its HITRUST reports and Corrective Action Plans (CAPs), with customers on a case by case basis. All audit reports are shared under explicit NDA in Cloudticity format between Cloudticity and party to receive materials. Audit reports can be requested by Cloudticity workforce members for customers or directly by Cloudticity customers.

The following process is used to request audit reports:

1. Email is sent to support@cloudticity.com. In the email, please specify the type of report being requested and any required timelines for the report.
2. Upon receipt of the email, a Zendesk ticket with the details of the request will be automatically created and assigned to the Cloudticity Security Officer or Privacy Officer. Zendesk is a ticket management application used to track request status and outcomes.
3. Cloudticity will confirm if a current NDA is in place with the party requesting the audit report. If there is no NDA in place, Cloudticity will send one for execution.
4. Once it has been confirmed that an NDA is executed, the Cloudticity Security Officer or Privacy Officer must approve or reject the request. If the request is rejected, Cloudticity will notify the requesting party that we cannot share the requested report and solve the Zendesk ticket.
4. If the request is approved, Cloudticity will send the customer the requested audit report and solve the Zendesk ticket.

## 1.6 Version Control

Refer to the GitHub repository at [https://github.com/cloudticity/policies/](https://github.com/cloudticity/policies/) for the full version history of these policies.
