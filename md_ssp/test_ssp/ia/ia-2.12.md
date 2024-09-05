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
  sort-id: ia-02.12
---

# ia-2.12 - \[Identification and Authentication\] Acceptance of PIV Credentials

## Control Statement

Accept and electronically verify Personal Identity Verification-compliant credentials.

- \[12_fr\]

## Control Assessment Objective

Personal Identity Verification-compliant credentials are accepted and electronically verified.

## Control guidance

Include Common Access Card (CAC), i.e., the DoD technical implementation of PIV/FIPS 201/HSPD-12.

Acceptance of Personal Identity Verification (PIV)-compliant credentials applies to organizations implementing logical access control and physical access control systems. PIV-compliant credentials are those credentials issued by federal agencies that conform to FIPS Publication 201 and supporting guidance documents. The adequacy and reliability of PIV card issuers are authorized using [SP 800-79-2](#10963761-58fc-4b20-b3d6-b44a54daba03) . Acceptance of PIV-compliant credentials includes derived PIV credentials, the use of which is addressed in [SP 800-166](#e8552d48-cf41-40aa-8b06-f45f7fb4706c) . The DOD Common Access Card (CAC) is an example of a PIV credential.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ia-2.12 -->

#### Implementation Status: planned

### ocp4

Acceptance and electronic verification of Personal
Identity Verification (PIV) credentials is the responsibility
of the organizational identity provider (such as
LDAP, Active Directory, Red Hat SSO, etc).

To aid system administrators, documentation on
supported authentication providers can be found in the
OpenShift product documentation:

https://docs.openshift.com/container-platform/latest/authentication/understanding-identity-provider.html

#### Rules:

  - ocp_idp_no_htpasswd

#### Implementation Status: implemented

______________________________________________________________________
