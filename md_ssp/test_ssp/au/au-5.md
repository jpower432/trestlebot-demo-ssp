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
    - name: audit_error_alert_exists
      description: 'OpenShift audit works at the API server level, logging all requests
        coming to the server. However, if API server instance is unable to write errors,
        an alert must be issued in order for the organization to take a relevant action.
        e.g. shutting down that instance. Kubernetes by default has metrics that enable
        one to write such alerts: apiserver_audit_event_total apiserver_audit_error_total
        Such an example is shipped in OCP 4.9+ apiVersion: monitoring.coreos.com/v1
        kind: PrometheusRule metadata: name: audit-errors namespace: openshift-kube-apiserver
        spec: groups: - name: apiserver-audit rules: - alert: AuditLogError annotations:
        summary: |- An API Server instance was unable to write audit logs. This could
        be triggered by the node running out of space, or a malicious actor tampering
        with the audit logs. description: An API Server had an error writing to an
        audit log. expr: | sum by (apiserver,instance)(rate(apiserver_audit_error_total{apiserver=~".+-apiserver"}[5m]))
        / sum by (apiserver,instance) (rate(apiserver_audit_event_total{apiserver=~".+-apiserver"}[5m]))
        > 0 for: 1m labels: severity: warning For more information, consult the official
        Kubernetes documentation.'
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
  au-05_odp.01:
    alt-identifier: au-5_prm_1
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  au-05_odp.02:
    alt-identifier: au-5_prm_2
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  au-05_odp.03:
    guidelines:
      - prose: additional actions to be taken in the event of an audit logging process
          failure are defined;
    alt-identifier: au-5_prm_3
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
  sort-id: au-05
---

# au-5 - \[Audit and Accountability\] Response to Audit Logging Process Failures

## Control Statement

- \[a.\] Alert [personnel or roles] within [time period] in the event of an audit logging process failure; and

- \[b.\] Take the following additional actions: [additional actions].

## Control Assessment Objective

- \[AU-05a.\] [personnel or roles] are alerted in the event of an audit logging process failure within [time period];

- \[AU-05b.\] [additional actions] are taken in the event of an audit logging process failure.

## Control guidance

Audit logging process failures include software and hardware errors, failures in audit log capturing mechanisms, and reaching or exceeding audit log storage capacity. Organization-defined actions include overwriting oldest audit records, shutting down the system, and stopping the generation of audit records. Organizations may choose to define additional actions for audit logging process failures based on the type of failure, the location of the failure, the severity of the failure, or a combination of such factors. When the audit logging process failure is related to storage, the response is carried out for the audit log storage repository (i.e., the distinct system component where the audit logs are stored), the system on which the audit logs reside, the total audit log storage capacity of the organization (i.e., all audit log storage repositories combined), or all three. Organizations may decide to take no additional actions after alerting designated roles or personnel.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: au-5 -->

#### Implementation Status: planned

### ocp4

REPLACE_ME

#### Rules:

  - audit_error_alert_exists

#### Implementation Status: implemented

______________________________________________________________________
