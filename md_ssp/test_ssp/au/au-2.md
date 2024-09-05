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
    - name: directory_access_var_log_kube_audit
      description: The audit system should collect access events to read the Kubernetes
        audit log directory. The following audit rule will assure that access to audit
        log directory are collected. -a always,exit -F dir=/var/log/kube-apiserver/
        -F perm=r -F auid>=1000 -F auid!=unset -F key=access-audit-trail If the auditd
        daemon is configured to use the augenrules program to read audit rules during
        daemon startup (the default), add the rule to a file with suffix .rules in
        the directory /etc/audit/rules.d. If the auditd daemon is configured to use
        the auditctl utility to read audit rules during daemon startup, add the rule
        to /etc/audit/audit.rules file.
    - name: directory_access_var_log_oauth_audit
      description: The audit system should collect access events to read the OAuth
        audit log directory. The following audit rule will assure that access to audit
        log directory are collected. -a always,exit -F dir=/var/log/oauth-apiserver/
        -F perm=r -F auid>=1000 -F auid!=unset -F key=access-audit-trail If the auditd
        daemon is configured to use the augenrules program to read audit rules during
        daemon startup (the default), add the rule to a file with suffix .rules in
        the directory /etc/audit/rules.d. If the auditd daemon is configured to use
        the auditctl utility to read audit rules during daemon startup, add the rule
        to /etc/audit/audit.rules file.
    - name: directory_access_var_log_ocp_audit
      description: The audit system should collect access events to read the OpenShift
        audit log directory. The following audit rule will assure that access to audit
        log directory are collected. -a always,exit -F dir=/var/log/openshift-apiserver/
        -F perm=r -F auid>=1000 -F auid!=unset -F key=access-audit-trail If the auditd
        daemon is configured to use the augenrules program to read audit rules during
        daemon startup (the default), add the rule to a file with suffix .rules in
        the directory /etc/audit/rules.d. If the auditd daemon is configured to use
        the auditctl utility to read audit rules during daemon startup, add the rule
        to /etc/audit/audit.rules file.
    - name: audit_profile_set
      description: "OpenShift can audit the details of requests made to the API server
        through the standard Kubernetes audit capabilities. In OpenShift, auditing
        of the API Server is on by default. Audit provides a security-relevant chronological
        set of records documenting the sequence of activities that have affected system
        by individual users, administrators, or other components of the system. Audit
        works at the API server level, logging all requests coming to the server.
        Each audit log contains two entries: The request line containing: A Unique
        ID allowing to match the response line (see #2) The source IP of the request
        The HTTP method being invoked The original user invoking the operation The
        impersonated user for the operation (self meaning himself) The impersonated
        group for the operation (lookup meaning user's group) The namespace of the
        request or none The URI as requested The response line containing: The aforementioned
        unique ID The response code For more information on how to configure the audit
        profile, please visit the documentation"
x-trestle-rules-params:
  ocp4:
    - name: var_openshift_audit_profile
      description: Audit log profiles define how to log requests that come to the
        OpenShift API server, the Kubernetes API server, and the OAuth API server.
      options: "{'default': 'Default', 'Default': 'Default', 'WriteRequestBodies':
        'WriteRequestBodies', 'AllRequestBodies': 'AllRequestBodies'}"
      rule-id: audit_profile_set
x-trestle-comp-def-rules-param-vals:
  # You may set new values for rule parameters by adding
  #
  # ssp-values:
  #   - value 1
  #   - value 2
  #
  # below a section of values:
  # The values list refers to the values as set by the components, and the ssp-values are the new values
  # to be placed in SetParameters of the SSP.
  #
  ocp4:
    - name: var_openshift_audit_profile
      values:
        - WriteRequestBodies
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
  au-2_prm_2:
    aggregates:
      - au-02_odp.02
      - au-02_odp.03
    profile-param-value-origin: <REPLACE_ME>
  au-02_odp.01:
    guidelines:
      - prose: the event types that the system is capable of logging in support of
          the audit function are defined;
    alt-identifier: au-2_prm_1
    profile-param-value-origin: <REPLACE_ME>
  au-02_odp.02:
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  au-02_odp.03:
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  au-02_odp.04:
    guidelines:
      - prose: the frequency of event types selected for logging are reviewed and
          updated;
    alt-identifier: au-2_prm_3
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
  sort-id: au-02
---

# au-2 - \[Audit and Accountability\] Event Logging

## Control Statement

- \[a.\] Identify the types of events that the system is capable of logging in support of the audit function: [event types];

- \[b.\] Coordinate the event logging function with other organizational entities requiring audit-related information to guide and inform the selection criteria for events to be logged;

- \[c.\] Specify the following event types for logging within the system: [organization-defined event types (subset of the event types defined in [AU-2a.](#au-2_smt.a)) along with the frequency of (or situation requiring) logging for each identified event type];

- \[d.\] Provide a rationale for why the event types selected for logging are deemed to be adequate to support after-the-fact investigations of incidents; and

- \[e.\] Review and update the event types selected for logging [frequency].

- \[au-2_fr\]

  - \[Requirement:\] Coordination between service provider and consumer shall be documented and accepted by the JAB/AO.

## Control Assessment Objective

- \[AU-02a.\] [event types] that the system is capable of logging are identified in support of the audit logging function;

- \[AU-02b.\] the event logging function is coordinated with other organizational entities requiring audit-related information to guide and inform the selection criteria for events to be logged;

- \[AU-02c.\]

  - \[AU-02c.[01]\] [event types (subset of AU-02_ODP[01])] are specified for logging within the system;
  - \[AU-02c.[02]\] the specified event types are logged within the system [frequency or situation];

- \[AU-02d.\] a rationale is provided for why the event types selected for logging are deemed to be adequate to support after-the-fact investigations of incidents;

- \[AU-02e.\] the event types selected for logging are reviewed and updated [frequency].

## Control guidance

Annually or whenever changes in the threat environment are communicated to the service provider by the JAB/AO.

An event is an observable occurrence in a system. The types of events that require logging are those events that are significant and relevant to the security of systems and the privacy of individuals. Event logging also supports specific monitoring and auditing needs. Event types include password changes, failed logons or failed accesses related to systems, security or privacy attribute changes, administrative privilege usage, PIV credential usage, data action changes, query parameters, or external credential usage. In determining the set of event types that require logging, organizations consider the monitoring and auditing appropriate for each of the controls to be implemented. For completeness, event logging includes all protocols that are operational and supported by the system.

To balance monitoring and auditing requirements with other system needs, event logging requires identifying the subset of event types that are logged at a given point in time. For example, organizations may determine that systems need the capability to log every file access successful and unsuccessful, but not activate that capability except for specific circumstances due to the potential burden on system performance. The types of events that organizations desire to be logged may change. Reviewing and updating the set of logged events is necessary to help ensure that the events remain relevant and continue to support the needs of the organization. Organizations consider how the types of logging events can reveal information about individuals that may give rise to privacy risk and how best to mitigate such risks. For example, there is the potential to reveal personally identifiable information in the audit trail, especially if the logging event is based on patterns or time of usage.

Event logging requirements, including the need to log specific event types, may be referenced in other controls and control enhancements. These include [AC-2(4)](#ac-2.4), [AC-3(10)](#ac-3.10), [AC-6(9)](#ac-6.9), [AC-17(1)](#ac-17.1), [CM-3f](#cm-3_smt.f), [CM-5(1)](#cm-5.1), [IA-3(3)(b)](#ia-3.3_smt.b), [MA-4(1)](#ma-4.1), [MP-4(2)](#mp-4.2), [PE-3](#pe-3), [PM-21](#pm-21), [PT-7](#pt-7), [RA-8](#ra-8), [SC-7(9)](#sc-7.9), [SC-7(15)](#sc-7.15), [SI-3(8)](#si-3.8), [SI-4(22)](#si-4.22), [SI-7(8)](#si-7.8) , and [SI-10(1)](#si-10.1) . Organizations include event types that are required by applicable laws, executive orders, directives, policies, regulations, standards, and guidelines. Audit records can be generated at various levels, including at the packet level as information traverses the network. Selecting the appropriate level of event logging is an important part of a monitoring and auditing capability and can identify the root causes of problems. When defining event types, organizations consider the logging necessary to cover related event types, such as the steps in distributed, transaction-based processes and the actions that occur in service-oriented architectures.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: au-2 -->

#### Implementation Status: planned

### ocp4

REPLACE_ME

#### Rules:

  - directory_access_var_log_kube_audit
  - audit_profile_set
  - directory_access_var_log_oauth_audit
  - directory_access_var_log_ocp_audit

#### Implementation Status: implemented

______________________________________________________________________
