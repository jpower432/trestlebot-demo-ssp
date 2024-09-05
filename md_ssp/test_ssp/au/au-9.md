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
    - name: directory_permissions_var_log_oauth_audit
      description: 'To properly set the permissions of /var/log/oauth-apiserver/,
        run the command: $ sudo chmod 0700 /var/log/oauth-apiserver/'
    - name: directory_permissions_var_log_kube_audit
      description: 'To properly set the permissions of /var/log/kube-apiserver/, run
        the command: $ sudo chmod 0700 /var/log/kube-apiserver/'
    - name: directory_permissions_var_log_ocp_audit
      description: 'To properly set the permissions of /var/log/openshift-apiserver/,
        run the command: $ sudo chmod 0700 /var/log/openshift-apiserver/'
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
    - name: audit_log_forwarding_uses_tls
      description: 'OpenShift audit works at the API server level, logging all requests
        coming to the server. Audit is on by default and the best practice is to ship
        audit logs off the cluster for retention using a secure protocol. The cluster-logging-operator
        is able to do this with the ClusterLogForwarders resource. The forementioned
        resource can be configured to logs to different third party systems. For more
        information on this, please reference the official documentation: https://docs.openshift.com/container-platform/latest/logging/cluster-logging-external.html'
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
  au-09_odp:
    alt-identifier: au-9_prm_1
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
  sort-id: au-09
---

# au-9 - \[Audit and Accountability\] Protection of Audit Information

## Control Statement

- \[a.\] Protect audit information and audit logging tools from unauthorized access, modification, and deletion; and

- \[b.\] Alert [personnel or roles] upon detection of unauthorized access, modification, or deletion of audit information.

## Control Assessment Objective

- \[AU-09a.\] audit information and audit logging tools are protected from unauthorized access, modification, and deletion;

- \[AU-09b.\] [personnel or roles] are alerted upon detection of unauthorized access, modification, or deletion of audit information.

## Control guidance

Audit information includes all information needed to successfully audit system activity, such as audit records, audit log settings, audit reports, and personally identifiable information. Audit logging tools are those programs and devices used to conduct system audit and logging activities. Protection of audit information focuses on technical protection and limits the ability to access and execute audit logging tools to authorized individuals. Physical protection of audit information is addressed by both media protection controls and physical and environmental protection controls.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: au-9 -->

#### Implementation Status: planned

### ocp4

Access to and integrity of the audit records on the master nodes
is protected by the usual operating system permissions.

This control is met when /var/log/kube-apiserver,
/var/log/openshift-apiserver and /var/log/oauth-apiserver have
the permissions 0700 and the files under them 0600 and are
owned by root.root.

In addition, if audit logs are being offloaded from the cluster
using Cluster Logging Operator, care must be taken to only
use TLS in transit - all ClusterLogForwarder outputs must use
either https:// or tls:// as protocol. For more information, see
https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-external.html

#### Rules:

  - directory_permissions_var_log_oauth_audit
  - audit_log_forwarding_uses_tls
  - directory_permissions_var_log_kube_audit
  - audit_profile_set
  - directory_permissions_var_log_ocp_audit

#### Implementation Status: implemented

______________________________________________________________________
