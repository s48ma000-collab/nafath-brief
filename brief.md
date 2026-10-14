Version: NAFATH-V1

Track: Software

## Overview
A national digital login service allows citizens to access multiple government services using one account. Software standards help verify users’ identities and control access to protected resources. Artificial intelligence can help detect suspicious login attempts, but its accuracy and risks must be assessed before deployment. Mobile applications should request only the permissions they need to protect users’ privacy. Secure networking, including DNS over HTTPS, can protect DNS queries during transmission, although it does not hide all online activity. Phishing-resistant authentication helps reduce the risk of attackers stealing login credentials. Data protection requirements also guide how citizens’ personal information is collected, processed, and stored. Together, these areas support a secure and trustworthy digital service. A key software question is how OAuth 2.0 differs from OpenID Connect, particularly in delegated access to resources and verifying a user’s identity.

## Software
OAuth 2.0 and OpenID Connect serve related but different purposes. OAuth 2.0 allows an application to obtain limited access to protected resources using access tokens. OpenID Connect adds an identity layer on top of OAuth 2.0, allowing a client to verify a user's identity through an ID Token. For a national login service, this distinction matters because confirming who the user is differs from deciding which resources an application can access.

Resource: OpenID Connect Core 1.0 - https://openid.net/specs/openid-connect-core-1_0.html

## AI
Before deploying an AI model to flag suspicious login attempts, the organization should assess its risks and test how reliably it identifies unusual activity. The model may incorrectly flag legitimate users or miss suspicious behavior. The NIST AI Risk Management Framework helps organizations manage AI risks and consider trustworthiness, including validity, reliability, security, transparency, privacy, and fairness. Monitoring the model after deployment is also important.

Resource: NIST AI Risk Management Framework - https://www.nist.gov/itl/ai-risk-management-framework

## Mobile
Android runtime permissions control access to certain device features and personal data. When an app needs a permission that requires user approval, it should request it at the appropriate time and explain why it is needed. For a national login app, permissions should be limited to what the feature requires. Requesting unnecessary permissions can reduce user trust and create avoidable privacy risks.

Resource: Permissions on Android - https://developer.android.com/guide/topics/permissions/overview

## Networking
DNS over HTTPS (DoH) sends DNS queries and responses through HTTPS, encrypting them while they travel between the client and the DNS resolver. This makes it harder for other parties on the network to read or interfere with DNS requests. However, DoH does not hide all online activity or prevent every security threat. The DNS server and other parts of the network may still learn some information about the connection.

Resource: RFC 8484: DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484.html

## Cybersecurity
Phishing-resistant multi-factor authentication (MFA) helps protect users from fake login websites designed to steal credentials. CISA identifies FIDO/WebAuthn authentication as a widely available phishing-resistant method. It can use a security key or an authenticator built into a device. By contrast, SMS codes can be stolen through phishing and should not be treated as phishing-resistant. A national login service should prioritize stronger authentication methods.

Resource: Implementing Phishing-Resistant MFA - https://www.cisa.gov/sites/default/files/2023-01/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf

## Data
Oman’s Personal Data Protection Law and its Executive Regulations set requirements for organizations that process personal data. Depending on the circumstances, obligations may include obtaining consent, securing permits for specified types of data processing, maintaining processing records, and providing ways for individuals to exercise their rights. Organizations must also follow applicable breach-notification and cross-border data transfer requirements. These measures help protect citizens’ personal information in a national login service.

Resource: Personal Data Protection - Ministry of Transport, Communications and Information Technology, Oman - https://www.mtcit.gov.om/sectors/governance/personal

## Misconception in My Track
A common misconception is that OAuth 2.0 alone is a complete login protocol that tells an application who the user is. OAuth 2.0 is mainly designed to provide delegated access to protected resources. OpenID Connect adds an identity layer on top of OAuth 2.0 and allows a client to verify the user's identity using an ID Token. This distinction is important for a national login service because granting access to resources and verifying a person's identity are related but different tasks.

Evidence: OpenID Connect Core 1.0, Section 1: Introduction.

## Open Question
How can a national login service balance strong phishing-resistant authentication with accessibility for citizens who use older devices or have limited access to security keys?
