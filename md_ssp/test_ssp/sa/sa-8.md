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
  sa-8_prm_1:
    aggregates:
      - sa-08_odp.01
      - sa-08_odp.02
    profile-param-value-origin: <REPLACE_ME>
  sa-08_odp.01:
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  sa-08_odp.02:
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
  sort-id: sa-08
---

# sa-8 - \[System and Services Acquisition\] Security and Privacy Engineering Principles

## Control Statement

Apply the following systems security and privacy engineering principles in the specification, design, development, implementation, and modification of the system and system components: [organization-defined systems security and privacy engineering principles].

## Control Assessment Objective

- \[SA-08[01]\] [systems security engineering principles] are applied in the specification of the system and system components;

- \[SA-08[02]\] [systems security engineering principles] are applied in the design of the system and system components;

- \[SA-08[03]\] [systems security engineering principles] are applied in the development of the system and system components;

- \[SA-08[04]\] [systems security engineering principles] are applied in the implementation of the system and system components;

- \[SA-08[05]\] [systems security engineering principles] are applied in the modification of the system and system components;

- \[SA-08[06]\] [privacy engineering principles] are applied in the specification of the system and system components;

- \[SA-08[07]\] [privacy engineering principles] are applied in the design of the system and system components;

- \[SA-08[08]\] [privacy engineering principles] are applied in the development of the system and system components;

- \[SA-08[09]\] [privacy engineering principles] are applied in the implementation of the system and system components;

- \[SA-08[10]\] [privacy engineering principles] are applied in the modification of the system and system components.

## Control guidance

Systems security and privacy engineering principles are closely related to and implemented throughout the system development life cycle (see [SA-3](#sa-3) ). Organizations can apply systems security and privacy engineering principles to new systems under development or to systems undergoing upgrades. For existing systems, organizations apply systems security and privacy engineering principles to system upgrades and modifications to the extent feasible, given the current state of hardware, software, and firmware components within those systems.

The application of systems security and privacy engineering principles helps organizations develop trustworthy, secure, and resilient systems and reduces the susceptibility to disruptions, hazards, threats, and the creation of privacy problems for individuals. Examples of system security engineering principles include: developing layered protections; establishing security and privacy policies, architecture, and controls as the foundation for design and development; incorporating security and privacy requirements into the system development life cycle; delineating physical and logical security boundaries; ensuring that developers are trained on how to build secure software; tailoring controls to meet organizational needs; and performing threat modeling to identify use cases, threat agents, attack vectors and patterns, design patterns, and compensating controls needed to mitigate risk.

Organizations that apply systems security and privacy engineering concepts and principles can facilitate the development of trustworthy, secure systems, system components, and system services; reduce risk to acceptable levels; and make informed risk management decisions. System security engineering principles can also be used to protect against certain supply chain risks, including incorporating tamper-resistant hardware into a design.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: sa-8 -->

#### Implementation Status: planned

______________________________________________________________________