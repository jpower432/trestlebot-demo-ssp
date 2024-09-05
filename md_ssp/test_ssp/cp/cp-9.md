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
  cp-09_odp.01:
    alt-identifier: cp-9_prm_1
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  cp-09_odp.02:
    guidelines:
      - prose: frequency at which to conduct backups of user-level information consistent
          with recovery time and recovery point objectives is defined;
    alt-identifier: cp-9_prm_2
    profile-param-value-origin: <REPLACE_ME>
  cp-09_odp.03:
    guidelines:
      - prose: frequency at which to conduct backups of system-level information consistent
          with recovery time and recovery point objectives is defined;
    alt-identifier: cp-9_prm_3
    profile-param-value-origin: <REPLACE_ME>
  cp-09_odp.04:
    guidelines:
      - prose: frequency at which to conduct backups of system documentation consistent
          with recovery time and recovery point objectives is defined;
    alt-identifier: cp-9_prm_4
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
  sort-id: cp-09
---

# cp-9 - \[Contingency Planning\] System Backup

## Control Statement

- \[a.\] Conduct backups of user-level information contained in [system components] [frequency];

- \[b.\] Conduct backups of system-level information contained in the system [frequency];

- \[c.\] Conduct backups of system documentation, including security- and privacy-related documentation [frequency] ; and

- \[d.\] Protect the confidentiality, integrity, and availability of backup information.

- \[cp-9_fr\]

  - \[Requirement:\] The service provider shall determine what elements of the cloud environment require the Information System Backup control. The service provider shall determine how Information System Backup is going to be verified and appropriate periodicity of the check.
  - \[(a) Requirement:\] The service provider maintains at least three backup copies of user-level information (at least one of which is available online) or provides an equivalent alternative.
  - \[(b) Requirement:\] The service provider maintains at least three backup copies of system-level information (at least one of which is available online) or provides an equivalent alternative.
  - \[(c) Requirement:\] The service provider maintains at least three backup copies of information system documentation including security information (at least one of which is available online) or provides an equivalent alternative.

## Control Assessment Objective

- \[CP-09a.\] backups of user-level information contained in [system components] are conducted [frequency];

- \[CP-09b.\] backups of system-level information contained in the system are conducted [frequency];

- \[CP-09c.\] backups of system documentation, including security- and privacy-related documentation are conducted [frequency];

- \[CP-09d.\]

  - \[CP-09d.[01]\] the confidentiality of backup information is protected;
  - \[CP-09d.[02]\] the integrity of backup information is protected;
  - \[CP-09d.[03]\] the availability of backup information is protected.

## Control guidance

System-level information includes system state information, operating system software, middleware, application software, and licenses. User-level information includes information other than system-level information. Mechanisms employed to protect the integrity of system backups include digital signatures and cryptographic hashes. Protection of system backup information while in transit is addressed by [MP-5](#mp-5) and [SC-8](#sc-8) . System backups reflect the requirements in contingency plans as well as other organizational requirements for backing up information. Organizations may be subject to laws, executive orders, directives, regulations, or policies with requirements regarding specific categories of information (e.g., personal health information). Organizational personnel consult with the senior agency official for privacy and legal counsel regarding such requirements.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: cp-9 -->

#### Implementation Status: planned

______________________________________________________________________
