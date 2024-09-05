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
    - name: audit_log_forwarding_enabled
      description: 'OpenShift audit works at the API server level, logging all requests
        coming to the server. Audit is on by default and the best practice is to ship
        audit logs off the cluster for retention. The cluster-logging-operator is
        able to do this with the ClusterLogForwarders resource. The forementioned
        resource can be configured to logs to different third party systems. For more
        information on this, please reference the official documentation: https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-external.html'
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
  au-06_odp.01:
    guidelines:
      - prose: frequency at which system audit records are reviewed and analyzed is
          defined;
    alt-identifier: au-6_prm_1
    profile-param-value-origin: <REPLACE_ME>
  au-06_odp.02:
    alt-identifier: au-6_prm_2
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  au-06_odp.03:
    alt-identifier: au-6_prm_3
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
  sort-id: au-06
---

# au-6 - \[Audit and Accountability\] Audit Record Review, Analysis, and Reporting

## Control Statement

- \[a.\] Review and analyze system audit records [frequency] for indications of [inappropriate or unusual activity] and the potential impact of the inappropriate or unusual activity;

- \[b.\] Report findings to [personnel or roles] ; and

- \[c.\] Adjust the level of audit record review, analysis, and reporting within the system when there is a change in risk based on law enforcement information, intelligence information, or other credible sources of information.

- \[au-6_fr\]

  - \[Requirement:\] Coordination between service provider and consumer shall be documented and accepted by the JAB/AO. In multi-tenant environments, capability and means for providing review, analysis, and reporting to consumer for data pertaining to consumer shall be documented.

## Control Assessment Objective

- \[AU-06a.\] system audit records are reviewed and analyzed [frequency] for indications of [inappropriate or unusual activity] and the potential impact of the inappropriate or unusual activity;

- \[AU-06b.\] findings are reported to [personnel or roles];

- \[AU-06c.\] the level of audit record review, analysis, and reporting within the system is adjusted when there is a change in risk based on law enforcement information, intelligence information, or other credible sources of information.

## Control guidance

Audit record review, analysis, and reporting covers information security- and privacy-related logging performed by organizations, including logging that results from the monitoring of account usage, remote access, wireless connectivity, mobile device connection, configuration settings, system component inventory, use of maintenance tools and non-local maintenance, physical access, temperature and humidity, equipment delivery and removal, communications at system interfaces, and use of mobile code or Voice over Internet Protocol (VoIP). Findings can be reported to organizational entities that include the incident response team, help desk, and security or privacy offices. If organizations are prohibited from reviewing and analyzing audit records or unable to conduct such activities, the review or analysis may be carried out by other organizations granted such authority. The frequency, scope, and/or depth of the audit record review, analysis, and reporting may be adjusted to meet organizational needs based on new information received.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: au-6 -->

#### Implementation Status: planned

### ocp4

REPLACE_ME

#### Rules:

  - audit_log_forwarding_enabled
  - audit_profile_set

#### Implementation Status: implemented

______________________________________________________________________
