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
    - name: partition_for_var_log_kube_apiserver
      description: 'Kubernetes API server audit logs are stored in the /var/log/kube-apiserver
        directory. Partitioning Red Hat CoreOS is a Day 1 operation and cannot be
        changed afterwards. For documentation on how to add a MachineConfig manifest
        that specifies a separate /var/log/kube-apiserver partition, follow: https://docs.openshift.com/container-platform/latest/installing/installing_platform_agnostic/installing-platform-agnostic.html#installation-user-infra-machines-advanced_disk_installing-platform-agnostic
        Note that the Red Hat OpenShift documentation often references a block device,
        such as /dev/vda. The name of the available block devices depends on the underlying
        infrastructure (bare metal vs cloud), and often the specific instance type.
        For example in AWS, some instance types have NVMe drives (/dev/nvme*), others
        use /dev/xvda*. You will need to look for relevant documentation for your
        infrastructure around this. In many cases, the simplest thing is to boot a
        single machine with an Ignition configuration that just gives you SSH access,
        and inspect the block devices via e.g. the lsblk command. For physical hardware,
        a good best practice is to reference devices via the /dev/disk/by-id/ or /dev/disk/by-path
        links.'
    - name: partition_for_var_log_openshift_apiserver
      description: 'Openshift API server audit logs are stored in the /var/log/openshift-apiserver
        directory. Partitioning Red Hat CoreOS is a Day 1 operation and cannot be
        changed afterwards. For documentation on how to add a MachineConfig manifest
        that specifies a separate /var/log/openshift-apiserver partition, follow:
        https://docs.openshift.com/container-platform/latest/installing/installing_platform_agnostic/installing-platform-agnostic.html#installation-user-infra-machines-advanced_disk_installing-platform-agnostic
        Note that the Red Hat OpenShift documentation often references a block device,
        such as /dev/vda. The name of the available block devices depends on the underlying
        infrastructure (bare metal vs cloud), and often the specific instance type.
        For example in AWS, some instance types have NVMe drives (/dev/nvme*), others
        use /dev/xvda*. You will need to look for relevant documentation for your
        infrastructure around this. In many cases, the simplest thing is to boot a
        single machine with an Ignition configuration that just gives you SSH access,
        and inspect the block devices via e.g. the lsblk command. For physical hardware,
        a good best practice is to reference devices via the /dev/disk/by-id/ or /dev/disk/by-path
        links.'
    - name: partition_for_var_log_oauth_apiserver
      description: 'OpenShift OAuth server audit logs are stored in the /var/log/oauth-apiserver
        directory. Partitioning Red Hat CoreOS is a Day 1 operation and cannot be
        changed afterwards. For documentation on how to add a MachineConfig manifest
        that specifies a separate /var/log/oauth-apiserver partition, follow: https://docs.openshift.com/container-platform/latest/installing/installing_platform_agnostic/installing-platform-agnostic.html#installation-user-infra-machines-advanced_disk_installing-platform-agnostic
        Note that the Red Hat OpenShift documentation often references a block device,
        such as /dev/vda. The name of the available block devices depends on the underlying
        infrastructure (bare metal vs cloud), and often the specific instance type.
        For example in AWS, some instance types have NVMe drives (/dev/nvme*), others
        use /dev/xvda*. You will need to look for relevant documentation for your
        infrastructure around this. In many cases, the simplest thing is to boot a
        single machine with an Ignition configuration that just gives you SSH access,
        and inspect the block devices via e.g. the lsblk command. For physical hardware,
        a good best practice is to reference devices via the /dev/disk/by-id/ or /dev/disk/by-path
        links.'
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
  au-04_odp:
    alt-identifier: au-4_prm_1
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
  sort-id: au-04
---

# au-4 - \[Audit and Accountability\] Audit Log Storage Capacity

## Control Statement

Allocate audit log storage capacity to accommodate [audit log retention requirements].

## Control Assessment Objective

audit log storage capacity is allocated to accommodate [audit log retention requirements].

## Control guidance

Organizations consider the types of audit logging to be performed and the audit log processing requirements when allocating audit log storage capacity. Allocating sufficient audit log storage capacity reduces the likelihood of such capacity being exceeded and resulting in the potential loss or reduction of audit logging capability.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: au-4 -->

#### Implementation Status: planned

### ocp4

Red Hat OpenShift audit logs are stored under the /var/log directory
on the master nodes, in particular /var/log/kube-apiserver,
/var/log/openshift-apiserver and /var/log/oauth-apiserver. To make
sure there is enough space for these logs, ensure that each of
the above directories resides on a separate partition.

The following document describes creating additional partitions:
https://docs.openshift.com/container-platform/4.7/installing/installing_platform_agnostic/installing-platform-agnostic.html#installation-user-infra-machines-advanced_disk_installing-platform-agnostic

#### Rules:

  - partition_for_var_log_kube_apiserver
  - partition_for_var_log_openshift_apiserver
  - partition_for_var_log_oauth_apiserver

#### Implementation Status: implemented

______________________________________________________________________
