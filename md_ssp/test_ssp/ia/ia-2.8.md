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
    - name: idp_is_configured
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
        | OpenShift Container Platform OpenShift includes built-in role based access
        control (RBAC) to determine whether a user is allowed to perform a given action
        within the cluster. Roles can have cluster scope or local (i.e. project) scope.
        Using RBAC to define and apply permissions | Authentication | OpenShift Container
        Platform
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
    - name: ocp_no_ldap_insecure
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
        | OpenShift Container Platform If the identity provider is LDAP, setting the
        insecure flag to true would mean that passwords, such as the one used to authenticate
        the OAuth proxy to the LDAP server would be transmitted in the clear, potentially
        allowing an attacker to read the password if they captured the network traffic.
x-trestle-set-params:
  # You may set values for parameters in the assembled SSP by adding
  #
  # ssp-values:
  #   - value 1
  #   - value 2
  #
  # below a section of values:
  # The values list refers to the values in the resolved profile catalog, and the ssp-values represent new values
  # to be placed in SetParameters of the SSP.
  #
  ia-02.08_odp:
    alt-identifier: ia-2.8_prm_1
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
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
  sort-id: ia-02.08
---

# ia-2.8 - \[Identification and Authentication\] Access to Accounts — Replay Resistant

## Control Statement

Implement replay-resistant authentication mechanisms for access to [Selection (one or more): privileged accounts; non-privileged accounts].

## Control Assessment Objective

replay-resistant authentication mechanisms for access to [Selection (one or more): privileged accounts; non-privileged accounts] are implemented.

## Control guidance

Authentication processes resist replay attacks if it is impractical to achieve successful authentications by replaying previous authentication messages. Replay-resistant techniques include protocols that use nonces or challenges such as time synchronous or cryptographic authenticators.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ia-2.8 -->

#### Implementation Status: planned

### ocp4

OpenShift offers support for replay-resistant authentication
mechanisms, both for OpenShift console and 3rd party
authentication. Third party identity providers configured for
modern TLS is supported by OpenShift.

Please see the specific identity provider documentation:
https://docs.openshift.com/container-platform/latest/authentication/understanding-authentication.html

When using the LDAP provider, care must be taken to not set
the "insecure" flag so that TLS is used.

#### Rules:

  - ocp_no_ldap_insecure
  - idp_is_configured
  - ocp_idp_no_htpasswd

#### Implementation Status: implemented

______________________________________________________________________
