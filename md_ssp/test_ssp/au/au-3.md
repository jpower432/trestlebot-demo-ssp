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
  sort-id: au-03
---

# au-3 - \[Audit and Accountability\] Content of Audit Records

## Control Statement

Ensure that audit records contain information that establishes the following:

- \[a.\] What type of event occurred;

- \[b.\] When the event occurred;

- \[c.\] Where the event occurred;

- \[d.\] Source of the event;

- \[e.\] Outcome of the event; and

- \[f.\] Identity of any individuals, subjects, or objects/entities associated with the event.

## Control Assessment Objective

- \[AU-03a.\] audit records contain information that establishes what type of event occurred;

- \[AU-03b.\] audit records contain information that establishes when the event occurred;

- \[AU-03c.\] audit records contain information that establishes where the event occurred;

- \[AU-03d.\] audit records contain information that establishes the source of the event;

- \[AU-03e.\] audit records contain information that establishes the outcome of the event;

- \[AU-03f.\] audit records contain information that establishes the identity of any individuals, subjects, or objects/entities associated with the event.

## Control guidance

Audit record content that may be necessary to support the auditing function includes event descriptions (item a), time stamps (item b), source and destination addresses (item c), user or process identifiers (items d and f), success or fail indications (item e), and filenames involved (items a, c, e, and f) . Event outcomes include indicators of event success or failure and event-specific results, such as the system security and privacy posture after the event occurred. Organizations consider how audit records can reveal information about individuals that may give rise to privacy risks and how best to mitigate such risks. For example, there is the potential to reveal personally identifiable information in the audit trail, especially if the trail records inputs or is based on patterns or time of usage.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: au-3 -->

#### Implementation Status: planned

### ocp4

Red Hat OpenShift enables auditing by default for the API Servers,
the OAuth server and the Linux hosts themselves. Auditing cannot
be turned off which makes the control inherently met.

The control asks for the following information to be audited:
  - what type of event occurred (verb is logged)
  - when the event occurred (timestamp is logged)
  - where the event occurred (request stage, the physical location of the file)
  - the source of the event (sourceIP, user are logged)
  - the outcome of the event (responseStatus is logged)
  - the identity of any individuals or subjects associated with
    the event (user UUID is logged which can be correlated with the real
    identity)

More documentation on what information Red Hat OpenShift audits can be found at:
https://docs.openshift.com/container-platform/4.7/security/audit-log-view.html
and:
https://docs.openshift.com/container-platform/4.7/security/audit-log-policy-config.html

#### Rules:

  - audit_profile_set

#### Implementation Status: implemented

______________________________________________________________________
