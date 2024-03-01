---
x-trestle-comp-def-rules:
  My Comp:
    - name: rule-ac-1
      description: Rule for ac-1
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
  ac-1_prm_1:
    aggregates:
      - ac-01_odp.01
      - ac-01_odp.02
    profile-param-value-origin: <REPLACE_ME>
  ac-01_odp.01:
    guidelines:
      - prose: personnel or roles to whom the access control policy is to be disseminated
          is/are defined;
    profile-param-value-origin: <REPLACE_ME>
  ac-01_odp.02:
    guidelines:
      - prose: personnel or roles to whom the access control procedures are to be
          disseminated is/are defined;
    profile-param-value-origin: <REPLACE_ME>
  ac-01_odp.03:
    alt-identifier: ac-1_prm_2
    profile-param-value-origin: <REPLACE_ME>
  ac-01_odp.04:
    guidelines:
      - prose: an official to manage the access control policy and procedures is defined;
    alt-identifier: ac-1_prm_3
    profile-param-value-origin: <REPLACE_ME>
  ac-01_odp.05:
    guidelines:
      - prose: the frequency at which the current access control policy is reviewed
          and updated is defined;
    alt-identifier: ac-1_prm_4
    profile-param-value-origin: <REPLACE_ME>
  ac-01_odp.06:
    guidelines:
      - prose: events that would require the current access control policy to be reviewed
          and updated are defined;
    alt-identifier: ac-1_prm_5
    profile-param-value-origin: <REPLACE_ME>
  ac-01_odp.07:
    guidelines:
      - prose: the frequency at which the current access control procedures are reviewed
          and updated is defined;
    alt-identifier: ac-1_prm_6
    profile-param-value-origin: <REPLACE_ME>
  ac-01_odp.08:
    guidelines:
      - prose: events that would require procedures to be reviewed and updated are
          defined;
    alt-identifier: ac-1_prm_7
    profile-param-value-origin: <REPLACE_ME>
x-trestle-global:
  profile:
    title: Example
    href: trestle://profiles/example/profile.json
  sort-id: ac-01
---

# ac-1 - \[Access Control\] Policy and Procedures

## Control Statement

- \[a.\] Develop, document, and disseminate to [organization-defined personnel or roles]:

  - \[1.\] [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy that:

    - \[(a)\] Addresses purpose, scope, roles, responsibilities, management commitment, coordination among organizational entities, and compliance; and
    - \[(b)\] Is consistent with applicable laws, executive orders, directives, regulations, policies, standards, and guidelines; and

  - \[2.\] Procedures to facilitate the implementation of the access control policy and the associated access controls;

- \[b.\] Designate an [official] to manage the development, documentation, and dissemination of the access control policy and procedures; and

- \[c.\] Review and update the current access control:

  - \[1.\] Policy [frequency] and following [events] ; and
  - \[2.\] Procedures [frequency] and following [events].

## Control Assessment Objective

- \[AC-01a.\]

  - \[AC-01a.[01]\] an access control policy is developed and documented;
  - \[AC-01a.[02]\] the access control policy is disseminated to [personnel or roles];
  - \[AC-01a.[03]\] access control procedures to facilitate the implementation of the access control policy and associated controls are developed and documented;
  - \[AC-01a.[04]\] the access control procedures are disseminated to [personnel or roles];
  - \[AC-01a.01\]

    - \[AC-01a.01(a)\]

      - \[AC-01a.01(a)[01]\] the [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy addresses purpose;
      - \[AC-01a.01(a)[02]\] the [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy addresses scope;
      - \[AC-01a.01(a)[03]\] the [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy addresses roles;
      - \[AC-01a.01(a)[04]\] the [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy addresses responsibilities;
      - \[AC-01a.01(a)[05]\] the [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy addresses management commitment;
      - \[AC-01a.01(a)[06]\] the [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy addresses coordination among organizational entities;
      - \[AC-01a.01(a)[07]\] the [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy addresses compliance;

    - \[AC-01a.01(b)\] the [Selection (one or more): organization-level; mission/business process-level; system-level] access control policy is consistent with applicable laws, Executive Orders, directives, regulations, policies, standards, and guidelines;

- \[AC-01b.\] the [official] is designated to manage the development, documentation, and dissemination of the access control policy and procedures;

- \[AC-01c.\]

  - \[AC-01c.01\]

    - \[AC-01c.01[01]\] the current access control policy is reviewed and updated [frequency];
    - \[AC-01c.01[02]\] the current access control policy is reviewed and updated following [events];

  - \[AC-01c.02\]

    - \[AC-01c.02[01]\] the current access control procedures are reviewed and updated [frequency];
    - \[AC-01c.02[02]\] the current access control procedures are reviewed and updated following [events].

## Control guidance

Access control policy and procedures address the controls in the AC family that are implemented within systems and organizations. The risk management strategy is an important factor in establishing such policies and procedures. Policies and procedures contribute to security and privacy assurance. Therefore, it is important that security and privacy programs collaborate on the development of access control policy and procedures. Security and privacy program policies and procedures at the organization level are preferable, in general, and may obviate the need for mission- or system-specific policies and procedures. The policy can be included as part of the general security and privacy policy or be represented by multiple policies reflecting the complex nature of organizations. Procedures can be established for security and privacy programs, for mission or business processes, and for systems, if needed. Procedures describe how the policies or controls are implemented and can be directed at the individual or role that is the object of the procedure. Procedures can be documented in system security and privacy plans or in one or more separate documents. Events that may precipitate an update to access control policy and procedures include assessment or audit findings, security incidents or breaches, or changes in laws, executive orders, directives, regulations, policies, standards, and guidelines. Simply restating controls does not constitute an organizational policy or procedure.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ac-1 -->

#### Implementation Status: planned

### My Comp

This is an example response.

#### Rules:

  - rule-ac-1

#### Implementation Status: planned

______________________________________________________________________
