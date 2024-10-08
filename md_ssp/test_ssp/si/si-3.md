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
  si-03_odp.01:
    alt-identifier: si-3_prm_1
    profile-param-value-origin: <REPLACE_ME>
  si-03_odp.02:
    guidelines:
      - prose: the frequency at which malicious code protection mechanisms perform
          scans is defined;
    alt-identifier: si-3_prm_2
    profile-param-value-origin: <REPLACE_ME>
  si-03_odp.03:
    alt-identifier: si-3_prm_3
    profile-param-value-origin: <REPLACE_ME>
  si-03_odp.04:
    alt-identifier: si-3_prm_4
    profile-param-value-origin: <REPLACE_ME>
  si-03_odp.05:
    guidelines:
      - prose: action to be taken in response to malicious code detection are defined
          (if selected);
    alt-identifier: si-3_prm_5
    profile-param-value-origin: <REPLACE_ME>
  si-03_odp.06:
    alt-identifier: si-3_prm_6
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
  sort-id: si-03
---

# si-3 - \[System and Information Integrity\] Malicious Code Protection

## Control Statement

- \[a.\] Implement [Selection (one or more): signature-based; non-signature-based] malicious code protection mechanisms at system entry and exit points to detect and eradicate malicious code;

- \[b.\] Automatically update malicious code protection mechanisms as new releases are available in accordance with organizational configuration management policy and procedures;

- \[c.\] Configure malicious code protection mechanisms to:

  - \[1.\] Perform periodic scans of the system [frequency] and real-time scans of files from external sources at [Selection (one or more): endpoint; network entry and exit points] as the files are downloaded, opened, or executed in accordance with organizational policy; and
  - \[2.\] [Selection (one or more): block malicious code; quarantine malicious code; take [action]] ; and send alert to [personnel or roles] in response to malicious code detection; and

- \[d.\] Address the receipt of false positives during malicious code detection and eradication and the resulting potential impact on the availability of the system.

## Control Assessment Objective

- \[SI-03a.\]

  - \[SI-03a.[01]\] [Selection (one or more): signature-based; non-signature-based] malicious code protection mechanisms are implemented at system entry and exit points to detect malicious code;
  - \[SI-03a.[02]\] [Selection (one or more): signature-based; non-signature-based] malicious code protection mechanisms are implemented at system entry and exit points to eradicate malicious code;

- \[SI-03b.\] malicious code protection mechanisms are updated automatically as new releases are available in accordance with organizational configuration management policy and procedures;

- \[SI-03c.\]

  - \[SI-03c.01\]

    - \[SI-03c.01[01]\] malicious code protection mechanisms are configured to perform periodic scans of the system [frequency];
    - \[SI-03c.01[02]\] malicious code protection mechanisms are configured to perform real-time scans of files from external sources at [Selection (one or more): endpoint; network entry and exit points] as the files are downloaded, opened, or executed in accordance with organizational policy;

  - \[SI-03c.02\]

    - \[SI-03c.02[01]\] malicious code protection mechanisms are configured to [Selection (one or more): block malicious code; quarantine malicious code; take [action]] in response to malicious code detection;
    - \[SI-03c.02[02]\] malicious code protection mechanisms are configured to send alerts to [personnel or roles] in response to malicious code detection;

- \[SI-03d.\] the receipt of false positives during malicious code detection and eradication and the resulting potential impact on the availability of the system are addressed.

## Control guidance

System entry and exit points include firewalls, remote access servers, workstations, electronic mail servers, web servers, proxy servers, notebook computers, and mobile devices. Malicious code includes viruses, worms, Trojan horses, and spyware. Malicious code can also be encoded in various formats contained within compressed or hidden files or hidden in files using techniques such as steganography. Malicious code can be inserted into systems in a variety of ways, including by electronic mail, the world-wide web, and portable storage devices. Malicious code insertions occur through the exploitation of system vulnerabilities. A variety of technologies and methods exist to limit or eliminate the effects of malicious code.

Malicious code protection mechanisms include both signature- and nonsignature-based technologies. Nonsignature-based detection mechanisms include artificial intelligence techniques that use heuristics to detect, analyze, and describe the characteristics or behavior of malicious code and to provide controls against such code for which signatures do not yet exist or for which existing signatures may not be effective. Malicious code for which active signatures do not yet exist or may be ineffective includes polymorphic malicious code (i.e., code that changes signatures when it replicates). Nonsignature-based mechanisms also include reputation-based technologies. In addition to the above technologies, pervasive configuration management, comprehensive software integrity controls, and anti-exploitation software may be effective in preventing the execution of unauthorized code. Malicious code may be present in commercial off-the-shelf software as well as custom-built software and could include logic bombs, backdoors, and other types of attacks that could affect organizational mission and business functions.

In situations where malicious code cannot be detected by detection methods or technologies, organizations rely on other types of controls, including secure coding practices, configuration management and control, trusted procurement processes, and monitoring practices to ensure that software does not perform functions other than the functions intended. Organizations may determine that, in response to the detection of malicious code, different actions may be warranted. For example, organizations can define actions in response to malicious code detection during periodic scans, the detection of malicious downloads, or the detection of maliciousness when attempting to open or execute files.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: si-3 -->

#### Implementation Status: planned

______________________________________________________________________
