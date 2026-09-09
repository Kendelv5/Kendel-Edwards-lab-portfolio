# Identity and Access Management (IAM) Lab Portfolio

Welcome to my IAM engineering and administration portfolio. This repository documents a series of hands-on homelabs designed to build, secure, and troubleshoot enterprise identity architectures using industry-leading cloud platforms like Okta and Microsoft Entra ID. I am a recent graduate of DeVry University's undergraduate cybersecurity program. My passion for technology and security comes from life lessons from being hacked and watching family losing credentials and become victims of ransomware. I love information security and the professionals who keep data protected.

The goal of this portfolio is to bridge theoretical security concepts with practical implementation, focusing on Zero Trust principles, automated identity lifecycles, and secure federation.

---

## 🛠️ Skills & Technologies Demonstrated
* **Identity Providers (IdP):** Okta Identity Engine (OIE), Microsoft Entra ID
* **Access Control:** Role-Based Access Control (RBAC), Attribute-Based Access Control (ABAC), Adaptive Multi-Factor Authentication (MFA)
* **Lifecycle Management (LCM):** Automated User Provisioning/Deprovisioning, Custom Group Rules, Expression Languages
* **Federation & Protocols:** SAML 2.0, OpenID Connect (OIDC)
* **Governance & Security:** Network Zones, Risk-Based Policies, Access Reviews

---

## 📁 Lab Directory

| Lab # | Project Title | Core Technologies | Description |
| :---: | :--- | :--- | :--- |
| **01** | [Automated Lifecycle Management](https://github.com/Kendelv5/.-01-Lifecycle-Management-) | Okta, Expression Language | Automated contractor provisioning and group assignment using custom attribute rules. |
| **02** | [Adaptive MFA & Network Zones](https://github.com/Kendelv5/Lab03-Adaptive-MFA-Network-Zones) | Okta OIE, Network Security | Enforced step-up authentication based on corporate network boundaries and device context. |
| **03** | [SAML 2.0 Federation](https://github.com/Kendelv5/Lab03-SAML-2.0-Federation/blob/main/README.md) | Okta IdP, SAML | Configured single sign-on (SSO) and attribute mapping between an identity provider and a service provider. |
| **04A** | [On-Premises JML Automation](https://github.com/Kendelv5/04-JML-Lifecycle-Automation) | Active Directory, OUs, GPOs | Structured an on-premises enterprise JML framework utilizing Organizational Units, security groups, and manual offboarding controls. |
| **04B** | [Cloud JML Lifecycle Automation](https://github.com/Kendelv5/04B-JML-Automation-OKTA) | Okta OIE, Lifecycle Workflows | Designed a complete cloud-native Joiner-Mover-Leaver lifecycle workflow handling automated transitions, department shifts, and secure offboarding. |
| **05** | [Entra ID Conditional Access](./05-Entra-Conditional-Access/) | Microsoft Entra ID, CA Policies | Implemented Zero Trust named locations and risk-based conditional access policies to enforce MFA dynamically. |
| **06** | [Identity Governance & Access Reviews](https://github.com/Kendelv5/06-Access-Reviews) | Microsoft Entra ID, Governance | Configured recurring access review campaigns with automated remediation to mitigate privilege creep and ensure compliance. |
| **07** | [Privileged Identity Management](https://github.com/Kendelv5/07-Privileged-Identity-Management) | Microsoft Entra ID, PIM | Eliminated standing admin rights by configuring Just-in-Time (JIT) role eligibility, approval workflows, and activation justifications. |
| **08** | [Identity Protection & Risk Policies](https://github.com/Kendelv5/08-Identity-Protection-Risk-Policies) | Microsoft Entra ID, Risk Engine | Implemented behavior-driven Conditional Access risk policies to automatically trigger remediation and secure compromised accounts. |
| **09** | [App Registrations & OIDC](https://github.com/Kendelv5/09-App-Registrations-OIDC) | Microsoft Entra ID, OIDC, OAuth 2.0 | Configured custom enterprise application objects, token flows, and confidential client credentials for modern application-level IAM integration. |
| **10** | [Entra ID Lifecycle Workflows](https://github.com/Kendelv5/10-Lifecycle-Workflows) | Microsoft Entra ID, Lifecycle Governance | Configured automated, cloud-native orchestration engines to execute scheduled offboarding tasks, session revocation, and account disabling. |
| **11** | [Enterprise Application Provisioning & SCIM](https://github.com/Kendelv5/11-SCIM-App-Provisioning) | Microsoft Entra ID, SCIM 2.0 | Established automated SaaS user synchronization pipelines, attribute mapping schemas, and endpoint connectivity handshakes. |
---

## 🚀 Lab Architecture & Implementation Highlights

### Lab 1: Lifecycle Management & Group Rules
* **Challenge:** Manually managing temporary or contractor accounts introduces severe security oversight risks and administrative drag.
* **Solution:** Configured custom user attributes and Okta Expression Language rules (`user.department == "Contractor"`) to dynamically route users into specific security groups upon account activation.
* **Key Takeaway:** Mastered evaluating expression syntax and testing automated state transitions.

### Lab 2: Adaptive Multi-Factor Authentication
* **Challenge:** Balancing frictionless user experience with strict organizational security requirements.
* **Solution:** Established IP-based Network Zones to separate trusted corporate environments from external spaces, applying sign-on policies that trigger step-up MFA only for out-of-band access or sensitive resources.

### Lab 3: Adaptive Multi-Factor Authentication
* **Challenge:** Balancing frictionless user experience with strict organizational security requirements.
* **Solution:** Established IP-based Network Zones to separate trusted corporate environments from external spaces, applying sign-on policies that trigger step-up MFA only for out-of-band access or sensitive resources.

### Lab 4A: JML Lifecycle Automation (Joiner-Mover-Leaver)
* **Challenge:** Ensuring seamless, secure permission updates when employees join, change roles internally, or leave the company without leaving orphaned accounts.
* **Solution:** Configured attribute-driven group rules to handle the **Joiner** phase (automatic app assignment), **Mover** phase (dynamic department/title updates, revoking old access and granting new apps), and **Leaver** phase (instant deactivation and suspension of active sessions).
* **Key Takeaway:** Built an automated state machine logic via identity attributes to drastically reduce administrative overhead and mitigate insider threat windows.

### Lab 4B: On-Premises JML (Active Directory)
* **Challenge:** Managing traditional corporate environments where employee transitions risk orphaned accounts and privilege creep without physical or structural segregation.
* **Solution:** Designed an AD OU hierarchy (`Corp/Users/Active/` vs `Corp/Users/Terminated/`) and automated departmental group provisioning to control the Joiner-Mover-Leaver pipeline.
* **Key Takeaway:** Gained foundational mastery of directory services, security scopes, and enterprise offboarding hygiene.

### Lab 5: Microsoft Entra ID Conditional Access
* **Challenge:** Replicating perimeter controls and risk management in a Microsoft cloud-centric environment.
* **Solution:** Created Trusted Named Locations in Entra ID and built Conditional Access policies to evaluate user location signals in real time, forcing step-up MFA when users log in from untrusted networks.

### Lab 6: Identity Governance & Access Reviews
* **Challenge:** Preventing privilege creep and maintaining regulatory compliance over static, long-term security group memberships.
* **Solution:** Implemented recurring quarterly Access Review campaigns in Entra ID, assigning management attestation responsibilities and enabling auto-apply remediation to instantly revoke access upon denial or non-response.

### Lab 7: Privileged Identity Management (PIM)
* **Challenge:** Minimizing the exposure window of privileged accounts by eliminating permanent standing administrative permissions.
* **Solution:** Configured Entra ID PIM role settings to enforce Just-in-Time (JIT) access, requiring explicit activation requests, business justifications, time-bounded sessions, and approval workflows.
* **Key Takeaway:** Mastered zero-standing privilege enforcement aligning directly with SC-300 enterprise security governance objectives.

### Lab 8: Identity Protection & Risk-Based Policies
* **Challenge:** Protecting corporate assets from real-time identity threats like leaked credentials and anomalous behavioral sign-ins.
* **Solution:** Built risk-driven Conditional Access policies evaluating high user-risk signals to automatically enforce risk remediation and password resets.
* **Key Takeaway:** Gained expertise in deploying self-healing security controls driven by cloud telemetry and machine learning risk engines.

### Lab 9: App Registrations & OpenID Connect (OIDC)
* **Challenge:** Integrating modern applications and APIs that rely on token-based OAuth/OIDC authorization instead of traditional user-facing federation protocols.
* **Solution:** Registered a custom enterprise application object (`OIDC-Test-Client-App`), configured implicit token grants, and provisioned confidential client credentials (`OIDC-Lab-Secret`).
* **Key Takeaway:** Expanded administrative scope from user directory controls into application-level identity architecture and developer token workflows.

### Lab 10: Microsoft Entra ID Lifecycle Workflows
* **Challenge:** Mitigating insider threats and administrative oversight during employee terminations and offboarding cycles.
* **Solution:** Deployed native Microsoft Entra ID Lifecycle Workflows (`Automated-Leaver-Offboarding`) to automate scheduled task execution, account deactivation, and session revocation.
* **Key Takeaway:** Mastered automated cloud orchestration to eliminate manual day-two administrative overhead and close security gaps left by delayed offboarding.

  ### Lab 11: Enterprise Application Provisioning & SCIM
* **Challenge:** Synchronizing user lifecycles and attributes across external SaaS platforms without relying on manual administrative intervention.
* **Solution:** Configured automated enterprise application provisioning using the SCIM protocol, establishing secure bearer token endpoint handshakes and managing attribute mapping schemas.
* **Key Takeaway:** Mastered automated SaaS identity synchronization, endpoint connectivity verification, and protocol-level attribute translation.
---
*Connect with me on [LinkedIn](https://www.linkedin.com/in/kendel-edwards-abb26aa7/) or reach out via email for inquiries.*
