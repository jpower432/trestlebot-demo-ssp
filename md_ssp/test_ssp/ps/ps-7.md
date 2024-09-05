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
  ps-07_odp.01:
    guidelines:
      - prose: personnel or roles to be notified of any personnel transfers or terminations
          of external personnel who possess organizational credentials and/or badges
          or who have system privileges is/are defined;
    alt-identifier: ps-7_prm_1
    profile-param-value-origin: <REPLACE_ME>
  ps-07_odp.02:
    guidelines:
      - prose: time period within which third-party providers are required to notify
          organization-defined personnel or roles of any personnel transfers or terminations
          of external personnel who possess organizational credentials and/or badges
          or who have system privileges is defined;
    alt-identifier: ps-7_prm_2
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
  sort-id: ps-07
---

# ps-7 - \[Personnel Security\] External Personnel Security

## Control Statement

- \[a.\] Establish personnel security requirements, including security roles and responsibilities for external providers;

- \[b.\] Require external providers to comply with personnel security policies and procedures established by the organization;

- \[c.\] Document personnel security requirements;

- \[d.\] Require external providers to notify [personnel or roles] of any personnel transfers or terminations of external personnel who possess organizational credentials and/or badges, or who have system privileges within [time period] ; and

- \[e.\] Monitor provider compliance with personnel security requirements.

## Control Assessment Objective

- \[PS-07a.\] personnel security requirements are established, including security roles and responsibilities for external providers;

- \[PS-07b.\] external providers are required to comply with personnel security policies and procedures established by the organization;

- \[PS-07c.\] personnel security requirements are documented;

- \[PS-07d.\] external providers are required to notify [personnel or roles] of any personnel transfers or terminations of external personnel who possess organizational credentials and/or badges or who have system privileges within [time period];

- \[PS-07e.\] provider compliance with personnel security requirements is monitored.

## Control guidance

External provider refers to organizations other than the organization operating or acquiring the system. External providers include service bureaus, contractors, and other organizations that provide system development, information technology services, testing or assessment services, outsourced applications, and network/security management. Organizations explicitly include personnel security requirements in acquisition-related documents. External providers may have personnel working at organizational facilities with credentials, badges, or system privileges issued by organizations. Notifications of external personnel changes ensure the appropriate termination of privileges and credentials. Organizations define the transfers and terminations deemed reportable by security-related characteristics that include functions, roles, and the nature of credentials or privileges associated with transferred or terminated individuals.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ps-7 -->

#### Implementation Status: planned

______________________________________________________________________
