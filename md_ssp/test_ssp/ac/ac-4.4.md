---
x-trestle-comp-def-rules:
  My Comp:
    - name: rule-ac-4.4
      description: Rule for ac-4.4 extra again
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
  ac-04.04_odp.01:
    guidelines:
      - prose: information flow control mechanisms that encrypted information is prevented
          from bypassing are defined;
    alt-identifier: ac-4.4_prm_1
    profile-param-value-origin: <REPLACE_ME>
  ac-04.04_odp.02:
    alt-identifier: ac-4.4_prm_2
    profile-param-value-origin: <REPLACE_ME>
  ac-04.04_odp.03:
    guidelines:
      - prose: the organization-defined procedure or method used to prevent encrypted
          information from bypassing information flow control mechanisms is defined
          (if selected);
    alt-identifier: ac-4.4_prm_3
    profile-param-value-origin: <REPLACE_ME>
x-trestle-global:
  profile:
    title: Example
    href: trestle://profiles/example/profile.json
  sort-id: ac-04.04
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
---

# ac-4.4 - \[Access Control\] Flow Control of Encrypted Information

## Control Statement

Prevent encrypted information from bypassing [information flow control mechanisms] by [Selection (one or more): decrypting the information; blocking the flow of the encrypted information; terminating communications sessions attempting to pass encrypted information; [organization-defined procedure or method]].

- \[4_fr\]

  - \[Requirement:\] The service provider must support Agency requirements to comply with M-21-31 (https://www.whitehouse.gov/wp-content/uploads/2021/08/M-21-31-Improving-the-Federal-Governments-Investigative-and-Remediation-Capabilities-Related-to-Cybersecurity-Incidents.pdf) and M-22-09 (https://www.whitehouse.gov/wp-content/uploads/2022/01/M-22-09.pdf).

## Control Assessment Objective

encrypted information is prevented from bypassing [information flow control mechanisms] by [Selection (one or more): decrypting the information; blocking the flow of the encrypted information; terminating communications sessions attempting to pass encrypted information; [organization-defined procedure or method]].

## Control guidance

Flow control mechanisms include content checking, security policy filters, and data type identifiers. The term encryption is extended to cover encoded data not recognized by filtering mechanisms.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ac-4.4 -->

#### Implementation Status: planned

### My Comp

<!-- Add control implementation description here for control: ac-4.4 -->

#### Rules:

  - rule-ac-4.4

#### Implementation Status: planned

______________________________________________________________________
