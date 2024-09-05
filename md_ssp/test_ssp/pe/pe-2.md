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
  pe-02_odp:
    guidelines:
      - prose: frequency at which to review the access list detailing authorized facility
          access by individuals is defined;
    alt-identifier: pe-2_prm_1
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
  sort-id: pe-02
---

# pe-2 - \[Physical and Environmental Protection\] Physical Access Authorizations

## Control Statement

- \[a.\] Develop, approve, and maintain a list of individuals with authorized access to the facility where the system resides;

- \[b.\] Issue authorization credentials for facility access;

- \[c.\] Review the access list detailing authorized facility access by individuals [frequency] ; and

- \[d.\] Remove individuals from the facility access list when access is no longer required.

## Control Assessment Objective

- \[PE-02a.\]

  - \[PE-02a.[01]\] a list of individuals with authorized access to the facility where the system resides has been developed;
  - \[PE-02a.[02]\] the list of individuals with authorized access to the facility where the system resides has been approved;
  - \[PE-02a.[03]\] the list of individuals with authorized access to the facility where the system resides has been maintained;

- \[PE-02b.\] authorization credentials are issued for facility access;

- \[PE-02c.\] the access list detailing authorized facility access by individuals is reviewed [frequency];

- \[PE-02d.\] individuals are removed from the facility access list when access is no longer required.

## Control guidance

Physical access authorizations apply to employees and visitors. Individuals with permanent physical access authorization credentials are not considered visitors. Authorization credentials include ID badges, identification cards, and smart cards. Organizations determine the strength of authorization credentials needed consistent with applicable laws, executive orders, directives, regulations, policies, standards, and guidelines. Physical access authorizations may not be necessary to access certain areas within facilities that are designated as publicly accessible.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: pe-2 -->

#### Implementation Status: planned

______________________________________________________________________
