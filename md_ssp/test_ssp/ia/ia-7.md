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
    - name: fips_mode_enabled_on_all_nodes
      description: 'OpenShift has an installation-time flag that can enable FIPS mode
        for the cluster. The flag fips: true must be enabled at install time in the
        install-config.yaml file.'
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
  sort-id: ia-07
---

# ia-7 - \[Identification and Authentication\] Cryptographic Module Authentication

## Control Statement

Implement mechanisms for authentication to a cryptographic module that meet the requirements of applicable laws, executive orders, directives, policies, regulations, standards, and guidelines for such authentication.

## Control Assessment Objective

mechanisms for authentication to a cryptographic module are implemented that meet the requirements of applicable laws, executive orders, directives, policies, regulations, standards, and guidelines for such authentication.

## Control guidance

Authentication mechanisms may be required within a cryptographic module to authenticate an operator accessing the module and to verify that the operator is authorized to assume the requested role and perform services within that role.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ia-7 -->

#### Implementation Status: planned

### ocp4

FIPS mode can be enabled in OpenShift through a flag that
can be set at installation time [1]. Follow the relevant
documentation for the applicable cloud provider [2][3][4][5]
for more information. But note that this is also applicable
in on-prem deployments.

[1] https://docs.openshift.com/container-platform/latest/installing/installing-fips.html
[2] https://docs.openshift.com/container-platform/latest/installing/installing_aws/installing-aws-government-region.html#installation-configuration-parameters_installing-aws-government-region
[3] https://docs.openshift.com/container-platform/4.7/installing/installing_azure/installing-azure-customizations.html
[4] https://docs.openshift.com/container-platform/4.7/installing/installing_gcp/installing-gcp-customizations.html

#### Rules:

  - fips_mode_enabled_on_all_nodes

#### Implementation Status: implemented

______________________________________________________________________
