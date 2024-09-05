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
x-trestle-comp-def-rules:
  ocp4:
    - name: openshift_motd_exists
      description: "To configure OpenShift's MOTD, create a ConfigMap called motd
        in the openshift namespace. The object should look as follows: --- apiVersion:
        v1 kind: ConfigMap metadata: name: motd namespace: openshift data: message:
        \"A relevant MOTD\" Where message is a mandatory key. The DoD required text
        is either: You are accessing a U.S. Government (USG) Information System (IS)
        that is provided for USG-authorized use only. By using this IS (which includes
        any device attached to this IS), you consent to the following conditions:
        -The USG routinely intercepts and monitors communications on this IS for purposes
        including, but not limited to, penetration testing, COMSEC monitoring, network
        operations and defense, personnel misconduct (PM), law enforcement (LE), and
        counterintelligence (CI) investigations. -At any time, the USG may inspect
        and seize data stored on this IS. -Communications using, or data stored on,
        this IS are not private, are subject to routine monitoring, interception,
        and search, and may be disclosed or used for any USG-authorized purpose. -This
        IS includes security measures (e.g., authentication and access controls) to
        protect USG interests -- not for your personal benefit or privacy. -Notwithstanding
        the above, using this IS does not constitute consent to PM, LE or CI investigative
        searching or monitoring of the content of privileged communications, or work
        product, related to personal representation or services by attorneys, psychotherapists,
        or clergy, and their assistants. Such communications and work product are
        private and confidential. See User Agreement for details. OR: I've read &
        consent to terms in IS user agreement."
    - name: banner_or_login_template_set
      description: A legal notice must be configured. This is achievable via the OAuth
        object by creating a custom login page, storing it in a Kubernetes Secret
        and referencing it in the appropriate field as described in the documentation
        Another way of achieving this is via a custom classification banner which
        is possible to set via the ConsoleNotification CRD as described in the documentation
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
  ac-08_odp.01:
    guidelines:
      - prose: system use notification message or banner to be displayed by the system
          to users before granting access to the system is defined;
    alt-identifier: ac-8_prm_1
    profile-param-value-origin: <REPLACE_ME>
  ac-08_odp.02:
    guidelines:
      - prose: conditions for system use to be displayed by the system before granting
          further access are defined;
    alt-identifier: ac-8_prm_2
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
  sort-id: ac-08
---

# ac-8 - \[Access Control\] System Use Notification

## Control Statement

- \[a.\] Display [system use notification] to users before granting access to the system that provides privacy and security notices consistent with applicable laws, executive orders, directives, regulations, policies, standards, and guidelines and state that:

  - \[1.\] Users are accessing a U.S. Government system;
  - \[2.\] System usage may be monitored, recorded, and subject to audit;
  - \[3.\] Unauthorized use of the system is prohibited and subject to criminal and civil penalties; and
  - \[4.\] Use of the system indicates consent to monitoring and recording;

- \[b.\] Retain the notification message or banner on the screen until users acknowledge the usage conditions and take explicit actions to log on to or further access the system; and

- \[c.\] For publicly accessible systems:

  - \[1.\] Display system use information [conditions] , before granting further access to the publicly accessible system;
  - \[2.\] Display references, if any, to monitoring, recording, or auditing that are consistent with privacy accommodations for such systems that generally prohibit those activities; and
  - \[3.\] Include a description of the authorized uses of the system.

- \[ac-8_fr\]

  - \[Requirement:\] The service provider shall determine elements of the cloud environment that require the System Use Notification control. The elements of the cloud environment that require System Use Notification are approved and accepted by the JAB/AO. 
  - \[Requirement:\] The service provider shall determine how System Use Notification is going to be verified and provide appropriate periodicity of the check. The System Use Notification verification and periodicity are approved and accepted by the JAB/AO.
  - \[Requirement:\] If not performed as part of a Configuration Baseline check, then there must be documented agreement on how to provide results of verification and the necessary periodicity of the verification by the service provider. The documented agreement on how to provide verification of the results are approved and accepted by the JAB/AO.

## Control Assessment Objective

- \[AC-08a.\] [system use notification] is displayed to users before granting access to the system that provides privacy and security notices consistent with applicable laws, Executive Orders, directives, regulations, policies, standards, and guidelines;

  - \[AC-08a.01\] the system use notification states that users are accessing a U.S. Government system;
  - \[AC-08a.02\] the system use notification states that system usage may be monitored, recorded, and subject to audit;
  - \[AC-08a.03\] the system use notification states that unauthorized use of the system is prohibited and subject to criminal and civil penalties; and
  - \[AC-08a.04\] the system use notification states that use of the system indicates consent to monitoring and recording;

- \[AC-08b.\] the notification message or banner is retained on the screen until users acknowledge the usage conditions and take explicit actions to log on to or further access the system;

- \[AC-08c.\]

  - \[AC-08c.01\] for publicly accessible systems, system use information [conditions] is displayed before granting further access to the publicly accessible system;
  - \[AC-08c.02\] for publicly accessible systems, any references to monitoring, recording, or auditing that are consistent with privacy accommodations for such systems that generally prohibit those activities are displayed;
  - \[AC-08c.03\] for publicly accessible systems, a description of the authorized uses of the system is included.

## Control guidance

If performed as part of a Configuration Baseline check, then the % of items requiring setting that are checked and that pass (or fail) check can be provided.

System use notifications can be implemented using messages or warning banners displayed before individuals log in to systems. System use notifications are used only for access via logon interfaces with human users. Notifications are not required when human interfaces do not exist. Based on an assessment of risk, organizations consider whether or not a secondary system use notification is needed to access applications or other system resources after the initial network logon. Organizations consider system use notification messages or banners displayed in multiple languages based on organizational needs and the demographics of system users. Organizations consult with the privacy office for input regarding privacy messaging and the Office of the General Counsel or organizational equivalent for legal review and approval of warning banner content.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: ac-8 -->

#### Implementation Status: planned

### ocp4

REPLACE_ME

#### Rules:

  - openshift_motd_exists
  - banner_or_login_template_set

#### Implementation Status: implemented

______________________________________________________________________
