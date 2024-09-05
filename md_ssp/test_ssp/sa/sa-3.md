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
  sa-03_odp:
    alt-identifier: sa-3_prm_1
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
  sort-id: sa-03
---

# sa-3 - \[System and Services Acquisition\] System Development Life Cycle

## Control Statement

- \[a.\] Acquire, develop, and manage the system using [system-development life cycle] that incorporates information security and privacy considerations;

- \[b.\] Define and document information security and privacy roles and responsibilities throughout the system development life cycle;

- \[c.\] Identify individuals having information security and privacy roles and responsibilities; and

- \[d.\] Integrate the organizational information security and privacy risk management process into system development life cycle activities.

## Control Assessment Objective

- \[SA-03a.\]

  - \[SA-03a.[01]\] the system is acquired, developed, and managed using [system-development life cycle] that incorporates information security considerations;
  - \[SA-03a.[02]\] the system is acquired, developed, and managed using [system-development life cycle] that incorporates privacy considerations;

- \[SA-03b.\]

  - \[SA-03b.[01]\] information security roles and responsibilities are defined and documented throughout the system development life cycle;
  - \[SA-03b.[02]\] privacy roles and responsibilities are defined and documented throughout the system development life cycle;

- \[SA-03c.\]

  - \[SA-03c.[01]\] individuals with information security roles and responsibilities are identified;
  - \[SA-03c.[02]\] individuals with privacy roles and responsibilities are identified;

- \[SA-03d.\]

  - \[SA-03d.[01]\] organizational information security risk management processes are integrated into system development life cycle activities;
  - \[SA-03d.[02]\] organizational privacy risk management processes are integrated into system development life cycle activities.

## Control guidance

A system development life cycle process provides the foundation for the successful development, implementation, and operation of organizational systems. The integration of security and privacy considerations early in the system development life cycle is a foundational principle of systems security engineering and privacy engineering. To apply the required controls within the system development life cycle requires a basic understanding of information security and privacy, threats, vulnerabilities, adverse impacts, and risk to critical mission and business functions. The security engineering principles in [SA-8](#sa-8) help individuals properly design, code, and test systems and system components. Organizations include qualified personnel (e.g., senior agency information security officers, senior agency officials for privacy, security and privacy architects, and security and privacy engineers) in system development life cycle processes to ensure that established security and privacy requirements are incorporated into organizational systems. Role-based security and privacy training programs can ensure that individuals with key security and privacy roles and responsibilities have the experience, skills, and expertise to conduct assigned system development life cycle activities.

The effective integration of security and privacy requirements into enterprise architecture also helps to ensure that important security and privacy considerations are addressed throughout the system life cycle and that those considerations are directly related to organizational mission and business processes. This process also facilitates the integration of the information security and privacy architectures into the enterprise architecture, consistent with the risk management strategy of the organization. Because the system development life cycle involves multiple organizations, (e.g., external suppliers, developers, integrators, service providers), acquisition and supply chain risk management functions and controls play significant roles in the effective management of the system during the life cycle.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: sa-3 -->

#### Implementation Status: planned

______________________________________________________________________