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
  ia-04_odp.01:
    guidelines:
      - prose: personnel or roles from whom authorization must be received to assign
          an identifier are defined;
    alt-identifier: ia-4_prm_1
    profile-param-value-origin: <REPLACE_ME>
  ia-04_odp.02:
    guidelines:
      - prose: a time period for preventing reuse of identifiers is defined;
    alt-identifier: ia-4_prm_2
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
  sort-id: ia-04
---

# ia-4 - \[Identification and Authentication\] Identifier Management

## Control Statement

Manage system identifiers by:

- \[a.\] Receiving authorization from [personnel or roles] to assign an individual, group, role, service, or device identifier;

- \[b.\] Selecting an identifier that identifies an individual, group, role, service, or device;

- \[c.\] Assigning the identifier to the intended individual, group, role, service, or device; and

- \[d.\] Preventing reuse of identifiers for [time period].

## Control Assessment Objective

- \[IA-04a.\] system identifiers are managed by receiving authorization from [personnel or roles] to assign to an individual, group, role, or device identifier;

- \[IA-04b.\] system identifiers are managed by selecting an identifier that identifies an individual, group, role, service, or device;

- \[IA-04c.\] system identifiers are managed by assigning the identifier to the intended individual, group, role, service, or device;

- \[IA-04d.\] system identifiers are managed by preventing reuse of identifiers for [time period].

## Control guidance

Common device identifiers include Media Access Control (MAC) addresses, Internet Protocol (IP) addresses, or device-unique token identifiers. The management of individual identifiers is not applicable to shared system accounts. Typically, individual identifiers are the usernames of the system accounts assigned to those individuals. In such instances, the account management activities of [AC-2](#ac-2) use account names provided by [IA-4](#ia-4) . Identifier management also addresses individual identifiers not necessarily associated with system accounts. Preventing the reuse of identifiers implies preventing the assignment of previously used individual, group, role, service, or device identifiers to different individuals, groups, roles, services, or devices.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ia-4 -->

#### Implementation Status: planned

______________________________________________________________________
