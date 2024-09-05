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
  ac-07_odp.01:
    alt-identifier: ac-7_prm_1
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  ac-07_odp.02:
    alt-identifier: ac-7_prm_2
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  ac-07_odp.03:
    alt-identifier: ac-7_prm_3
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  ac-07_odp.04:
    alt-identifier: ac-7_prm_4
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  ac-07_odp.05:
    alt-identifier: ac-7_prm_5
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  ac-07_odp.06:
    alt-identifier: ac-7_prm_6
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
  sort-id: ac-07
---

# ac-7 - \[Access Control\] Unsuccessful Logon Attempts

## Control Statement

- \[a.\] Enforce a limit of [number] consecutive invalid logon attempts by a user during a [time period] ; and

- \[b.\] Automatically [Selection (one or more): lock the account or node for [time period]; lock the account or node until released by an administrator; delay next logon prompt per [delay algorithm]; notify system administrator; take other [action]] when the maximum number of unsuccessful attempts is exceeded.

- \[ac-7_fr\]

  - \[Requirement:\] In alignment with NIST SP 800-63B

## Control Assessment Objective

- \[AC-07a.\] a limit of [number] consecutive invalid logon attempts by a user during [time period] is enforced;

- \[AC-07b.\] automatically [Selection (one or more): lock the account or node for [time period]; lock the account or node until released by an administrator; delay next logon prompt per [delay algorithm]; notify system administrator; take other [action]] when the maximum number of unsuccessful attempts is exceeded.

## Control guidance

The need to limit unsuccessful logon attempts and take subsequent action when the maximum number of attempts is exceeded applies regardless of whether the logon occurs via a local or network connection. Due to the potential for denial of service, automatic lockouts initiated by systems are usually temporary and automatically release after a predetermined, organization-defined time period. If a delay algorithm is selected, organizations may employ different algorithms for different components of the system based on the capabilities of those components. Responses to unsuccessful logon attempts may be implemented at the operating system and the application levels. Organization-defined actions that may be taken when the number of allowed consecutive invalid logon attempts is exceeded include prompting the user to answer a secret question in addition to the username and password, invoking a lockdown mode with limited user capabilities (instead of full lockout), allowing users to only logon from specified Internet Protocol (IP) addresses, requiring a CAPTCHA to prevent automated attacks, or applying user profiles such as location, time of day, IP address, device, or Media Access Control (MAC) address. If automatic system lockout or execution of a delay algorithm is not implemented in support of the availability objective, organizations consider a combination of other actions to help prevent brute force attacks. In addition to the above, organizations can prompt users to respond to a secret question before the number of allowed unsuccessful logon attempts is exceeded. Automatically unlocking an account after a specified period of time is generally not permitted. However, exceptions may be required based on operational mission or need.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ac-7 -->

#### Implementation Status: planned

### ocp4

REPLACE_ME

#### Rules:

  - ocp_idp_no_htpasswd
  - idp_is_configured

#### Implementation Status: implemented

______________________________________________________________________
