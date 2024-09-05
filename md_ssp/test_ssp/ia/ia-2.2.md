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
  sort-id: ia-02.02
---

# ia-2.2 - \[Identification and Authentication\] Multi-factor Authentication to Non-privileged Accounts

## Control Statement

Implement multi-factor authentication for access to non-privileged accounts.

- \[2_fr\]

  - \[Requirement:\] According to SP 800-63-3, SP 800-63A (IAL), SP 800-63B (AAL), and SP 800-63C (FAL).
  - \[Requirement:\] Multi-factor authentication must be phishing-resistant.

## Control Assessment Objective

multi-factor authentication for access to non-privileged accounts is implemented.

## Control guidance

Multi-factor authentication to subsequent components in the same user domain is not required.

Multi-factor authentication requires the use of two or more different factors to achieve authentication. The authentication factors are defined as follows: something you know (e.g., a personal identification number [PIN]), something you have (e.g., a physical authenticator such as a cryptographic private key), or something you are (e.g., a biometric). Multi-factor authentication solutions that feature physical authenticators include hardware authenticators that provide time-based or challenge-response outputs and smart cards such as the U.S. Government Personal Identity Verification card or the DoD Common Access Card. In addition to authenticating users at the system level, organizations may also employ authentication mechanisms at the application level, at their discretion, to provide increased information security. Regardless of the type of access (i.e., local, network, remote), non-privileged accounts are authenticated using multi-factor options appropriate for the level of risk. Organizations can provide additional security measures, such as additional or more rigorous authentication mechanisms, for specific types of access.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ia-2.2 -->

#### Implementation Status: planned

### ocp4

Implementing multifactor authentication for network access
to non-privileged accounts is the responsibility of the
organizational identity provider (such as
LDAP, Active Directory, Red Hat SSO, etc).

To aid system administrators, documentation on
supported authentication providers can be found in the
OpenShift product documentation:

https://docs.openshift.com/container-platform/latest/authentication/understanding-identity-provider.html

#### Rules:

  - ocp_idp_no_htpasswd

#### Implementation Status: implemented

______________________________________________________________________
