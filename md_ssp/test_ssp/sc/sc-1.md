---
x-trestle-comp-def-rules:
  My Comp:
    - name: rule-sc-1
      description: Rule for sc-1
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
  sc-1_prm_1:
    aggregates:
      - sc-01_odp.01
      - sc-01_odp.02
    profile-param-value-origin: <REPLACE_ME>
  sc-01_odp.01:
    guidelines:
      - prose: personnel or roles to whom the system and communications protection
          policy is to be disseminated is/are defined;
    profile-param-value-origin: <REPLACE_ME>
  sc-01_odp.02:
    guidelines:
      - prose: personnel or roles to whom the system and communications protection
          procedures are to be disseminated is/are defined;
    profile-param-value-origin: <REPLACE_ME>
  sc-01_odp.03:
    alt-identifier: sc-1_prm_2
    profile-param-value-origin: <REPLACE_ME>
  sc-01_odp.04:
    guidelines:
      - prose: an official to manage the system and communications protection policy
          and procedures is defined;
    alt-identifier: sc-1_prm_3
    profile-param-value-origin: <REPLACE_ME>
  sc-01_odp.05:
    guidelines:
      - prose: the frequency at which the current system and communications protection
          policy is reviewed and updated is defined;
    alt-identifier: sc-1_prm_4
    profile-param-value-origin: <REPLACE_ME>
  sc-01_odp.06:
    guidelines:
      - prose: events that would require the current system and communications protection
          policy to be reviewed and updated are defined;
    alt-identifier: sc-1_prm_5
    profile-param-value-origin: <REPLACE_ME>
  sc-01_odp.07:
    guidelines:
      - prose: the frequency at which the current system and communications protection
          procedures are reviewed and updated is defined;
    alt-identifier: sc-1_prm_6
    profile-param-value-origin: <REPLACE_ME>
  sc-01_odp.08:
    guidelines:
      - prose: events that would require the system and communications protection
          procedures to be reviewed and updated are defined;
    alt-identifier: sc-1_prm_7
    profile-param-value-origin: <REPLACE_ME>
x-trestle-global:
  profile:
    title: FedRAMP Rev 5 Low Baseline
    href: trestle://profiles/fedramp_rev5_low/profile.json
  sort-id: sc-01
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

# sc-1 - \[System and Communications Protection\] Policy and Procedures

## Control Statement

- \[a.\] Develop, document, and disseminate to [organization-defined personnel or roles]:

  - \[1.\] [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy that:

    - \[(a)\] Addresses purpose, scope, roles, responsibilities, management commitment, coordination among organizational entities, and compliance; and
    - \[(b)\] Is consistent with applicable laws, executive orders, directives, regulations, policies, standards, and guidelines; and

  - \[2.\] Procedures to facilitate the implementation of the system and communications protection policy and the associated system and communications protection controls;

- \[b.\] Designate an [official] to manage the development, documentation, and dissemination of the system and communications protection policy and procedures; and

- \[c.\] Review and update the current system and communications protection:

  - \[1.\] Policy [frequency] and following [events] ; and
  - \[2.\] Procedures [frequency] and following [events].

## Control Assessment Objective

- \[SC-01a.\]

  - \[SC-01a.[01]\] a system and communications protection policy is developed and documented;
  - \[SC-01a.[02]\] the system and communications protection policy is disseminated to [personnel or roles];
  - \[SC-01a.[03]\] system and communications protection procedures to facilitate the implementation of the system and communications protection policy and associated system and communications protection controls are developed and documented;
  - \[SC-01a.[04]\] the system and communications protection procedures are disseminated to [personnel or roles];
  - \[SC-01a.01\]

    - \[SC-01a.01(a)\]

      - \[SC-01a.01(a)[01]\] the [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy addresses purpose;
      - \[SC-01a.01(a)[02]\] the [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy addresses scope;
      - \[SC-01a.01(a)[03]\] the [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy addresses roles;
      - \[SC-01a.01(a)[04]\] the [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy addresses responsibilities;
      - \[SC-01a.01(a)[05]\] the [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy addresses management commitment;
      - \[SC-01a.01(a)[06]\] the [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy addresses coordination among organizational entities;
      - \[SC-01a.01(a)[07]\] the [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy addresses compliance;

    - \[SC-01a.01(b)\] the [Selection (one or more): organization-level; mission/business-process-level; system-level] system and communications protection policy is consistent with applicable laws, Executive Orders, directives, regulations, policies, standards, and guidelines;

- \[SC-01b.\] the [official] is designated to manage the development, documentation, and dissemination of the system and communications protection policy and procedures;

- \[SC-01c.\]

  - \[SC-01c.01\]

    - \[SC-01c.01[01]\] the current system and communications protection policy is reviewed and updated [frequency];
    - \[SC-01c.01[02]\] the current system and communications protection policy is reviewed and updated following [events];

  - \[SC-01c.02\]

    - \[SC-01c.02[01]\] the current system and communications protection procedures are reviewed and updated [frequency];
    - \[SC-01c.02[02]\] the current system and communications protection procedures are reviewed and updated following [events].

## Control guidance

System and communications protection policy and procedures address the controls in the SC family that are implemented within systems and organizations. The risk management strategy is an important factor in establishing such policies and procedures. Policies and procedures contribute to security and privacy assurance. Therefore, it is important that security and privacy programs collaborate on the development of system and communications protection policy and procedures. Security and privacy program policies and procedures at the organization level are preferable, in general, and may obviate the need for mission- or system-specific policies and procedures. The policy can be included as part of the general security and privacy policy or be represented by multiple policies that reflect the complex nature of organizations. Procedures can be established for security and privacy programs, for mission or business processes, and for systems, if needed. Procedures describe how the policies or controls are implemented and can be directed at the individual or role that is the object of the procedure. Procedures can be documented in system security and privacy plans or in one or more separate documents. Events that may precipitate an update to system and communications protection policy and procedures include assessment or audit findings, security incidents or breaches, or changes in applicable laws, executive orders, directives, regulations, policies, standards, and guidelines. Simply restating controls does not constitute an organizational policy or procedure.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: sc-1 -->

#### Implementation Status: planned

### My Comp

This is the responses for sc-1

#### Rules:

  - rule-sc-1

#### Implementation Status: planned

______________________________________________________________________
