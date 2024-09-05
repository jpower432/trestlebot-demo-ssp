---
x-trestle-add-props: []
  # Add or modify control properties here
  # Properties may be at the control or part level
  # Add control level properties like this:
  #   - name: ac1_new_prop
  #     value: new property value
  #
  # Add properties to a statement part like this, where "b." is the label of the target statement part
  #   - name: ac1_new_prop
  #     value: new property value
  #     smt-part: b.
  #
x-trestle-comp-def-rules:
  ocp4:
    - name: ocp_idp_no_htpasswd
      description: For users to interact with OpenShift Container Platform, they must
        first authenticate to the cluster. The authentication layer identifies the
        user associated with requests to the OpenShift Container Platform API. The
        authorization layer then uses information about the requesting user to determine
        if the request is allowed. Understanding authentication | Authentication |
        OpenShift Container Platform The OpenShift Container Platform includes a built-in
        OAuth server for token-based authentication. Developers and administrators
        obtain OAuth access tokens to authenticate themselves to the API. It is recommended
        for an administrator to configure OAuth to specify an identity provider after
        the cluster is installed. User access to the cluster is managed through the
        identity provider. Understanding identity provider configuration | Authentication
        | OpenShift Container Platform However, not all Identity Providers supported
        by OpenShift provide the same level of capabilities. As an example, the htpasswd
        Identity Provider only checks the username and password match and provides
        no means of 2FA, account lockout or notification mechanism. This rule therefore
        only allows a subset of identity providers.
x-trestle-fedramp-props:
  control-origination:
    - name: control-origination
      ns: https://fedramp.gov/ns/oscal
      value: sp-system
    - name: control-origination
      ns: https://fedramp.gov/ns/oscal
      value: sp-corporate
    - name: control-origination
      ns: https://fedramp.gov/ns/oscal
      value: customer-configured
    - name: control-origination
      ns: https://fedramp.gov/ns/oscal
      value: customer-provided
    - name: control-origination
      ns: https://fedramp.gov/ns/oscal
      value: inherited
x-trestle-global:
  profile:
    title: FedRAMP Rev 5 Low Baseline
    href: trestle://profiles/fedramp_rev5_low/profile.json
  sort-id: ia-02
---

# ia-2 - \[Identification and Authentication\] Identification and Authentication (Organizational Users)

## Control Statement

Uniquely identify and authenticate organizational users and associate that unique identification with processes acting on behalf of those users.

- \[ia-2_fr\]

  - \[Requirement:\] For all control enhancements that specify multifactor authentication, the implementation must adhere to the Digital Identity Guidelines specified in NIST Special Publication 800-63B.
  - \[Requirement:\] Multi-factor authentication must be phishing-resistant.

## Control Assessment Objective

- \[IA-02[01]\] organizational users are uniquely identified and authenticated;

- \[IA-02[02]\] the unique identification of authenticated organizational users is associated with processes acting on behalf of those users.

## Control guidance

\"Phishing-resistant\" authentication refers to authentication processes designed to detect and prevent disclosure of authentication secrets and outputs to a website or application masquerading as a legitimate system.

All uses of encrypted virtual private networks must meet all applicable Federal requirements and architecture, dataflow, and security and privacy controls must be documented, assessed, and authorized to operate.

Organizations can satisfy the identification and authentication requirements by complying with the requirements in [HSPD 12](#f16e438e-7114-4144-bfe2-2dfcad8cb2d0) . Organizational users include employees or individuals who organizations consider to have an equivalent status to employees (e.g., contractors and guest researchers). Unique identification and authentication of users applies to all accesses other than those that are explicitly identified in [AC-14](#ac-14) and that occur through the authorized use of group authenticators without individual authentication. Since processes execute on behalf of groups and roles, organizations may require unique identification of individuals in group accounts or for detailed accountability of individual activity.

Organizations employ passwords, physical authenticators, or biometrics to authenticate user identities or, in the case of multi-factor authentication, some combination thereof. Access to organizational systems is defined as either local access or network access. Local access is any access to organizational systems by users or processes acting on behalf of users, where access is obtained through direct connections without the use of networks. Network access is access to organizational systems by users (or processes acting on behalf of users) where access is obtained through network connections (i.e., nonlocal accesses). Remote access is a type of network access that involves communication through external networks. Internal networks include local area networks and wide area networks.

The use of encrypted virtual private networks for network connections between organization-controlled endpoints and non-organization-controlled endpoints may be treated as internal networks with respect to protecting the confidentiality and integrity of information traversing the network. Identification and authentication requirements for non-organizational users are described in [IA-8](#ia-8).

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ia-2 -->

#### Implementation Status: planned

### ocp4

Unique identification and authentication of organizational users
is deferred to the organizational identity provider (such as
LDAP, Active Directory, Red Hat SSO, etc). This part of the control
is not applicable to OpenShift.

To aid system administrators in configuring a centralized identity provider, documentation on
supported authentication providers can be found in the
OpenShift product documentation:

https://docs.openshift.com/container-platform/latest/authentication/understanding-authentication.html

The ability to uniquely identify processes acting on behalf of
organizational users, such as when a user deploys a new
container image, is provided by correlating system audit logs.

#### Rules:

  - ocp_idp_no_htpasswd

#### Implementation Status: implemented

______________________________________________________________________
