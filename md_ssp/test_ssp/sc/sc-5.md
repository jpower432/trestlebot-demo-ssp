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
    - name: routes_rate_limit
      description: OpenShift has an option to set the rate limit for Routes [1] when
        creating new Routes. All routes outside the openshift namespaces and the kube
        namespaces should use the rate-limiting annotations. [1] 
        https://docs.openshift.com/container-platform/4.9/networking/routes/route-configuration.html#nw-route-specific-annotations_route-configuration
    - name: resource_requests_quota
      description: 'There are two ways to enable resource requests and limits. To
        create either: A multi-project quota, defined by a ClusterResourceQuota object,
        allows quotas to be shared across multiple projects. Resources used in each
        selected project are aggregated and that aggregate is used to limit resources
        across all the selected projects. A resource quota, defined by a ResourceQuota
        object, provides constraints that limit aggregate resource consumption per
        project. It can limit the quantity of objects that can be created in a project
        by type, as well as the total amount of compute resources and storage that
        might be consumed by resources in that project. We want to make sure either
        a ClusterResourceQuota is used in a cluster or a ResourceQuota is used per
        namespaces. To configure ClusterResourceQuota, follow the directions in the
        documentation To configure ResourceQuota Per Project, follow the directions
        in the documentation'
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
  sc-05_odp.01:
    guidelines:
      - prose: types of denial-of-service events to be protected against or limited
          are defined;
    alt-identifier: sc-5_prm_2
    profile-param-value-origin: <REPLACE_ME>
  sc-05_odp.02:
    alt-identifier: sc-5_prm_1
    profile-param-value-origin: <REPLACE_ME>
  sc-05_odp.03:
    alt-identifier: sc-5_prm_3
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
  sort-id: sc-05
---

# sc-5 - \[System and Communications Protection\] Denial-of-service Protection

## Control Statement

- \[a.\] [Selection: protect against; limit] the effects of the following types of denial-of-service events: [types of denial-of-service events] ; and

- \[b.\] Employ the following controls to achieve the denial-of-service objective: [controls by type of denial-of-service event].

## Control Assessment Objective

- \[SC-05a.\] the effects of [types of denial-of-service events] are [Selection: protect against; limit];

- \[SC-05b.\] [controls by type of denial-of-service event] are employed to achieve the denial-of-service protection objective.

## Control guidance

Denial-of-service events may occur due to a variety of internal and external causes, such as an attack by an adversary or a lack of planning to support organizational needs with respect to capacity and bandwidth. Such attacks can occur across a wide range of network protocols (e.g., IPv4, IPv6). A variety of technologies are available to limit or eliminate the origination and effects of denial-of-service events. For example, boundary protection devices can filter certain types of packets to protect system components on internal networks from being directly affected by or the source of denial-of-service attacks. Employing increased network capacity and bandwidth combined with service redundancy also reduces the susceptibility to denial-of-service events.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: sc-5 -->

#### Implementation Status: planned

### ocp4

Depending on the exposure of the workloads or the component that's
intended to be protected, OpenShift offers several settings to enforce
rate-limiting and protection against denial of service attacks.

It is recommended that all workloads in the system establish appropriate
resource requests and limits to avoid resource starvation of critical
workloads. Appropriate configurations exist to manage resource
overcommitment [1]. Ensure that appropriate quotas are set in each
relevant project [2], or establish a cluster quota to limit the resources
that workloads can take [3].

OpenShift also allows the configuration of egress and ingress traffic
for individual workloads [4]. This ensures that workloads don't get
overwhelmed by incoming traffic, and that they don't act as Denial
of Service agents.

If a workload is to be exposed externally, it is recommended that it's
behind an OpenShift Route. Routes allow for the configuration of several
security attributes, but most relevant to this control is the rate-limiting
settings that it allows to configure in the form of annotations. configuring
rate-limiting settings for a workload exposed on a route not only protects
the workload itself, but also ensures that the target workload doesn't
interfere with other workloads placed on the same node or set of nodes.

On the other hand, OpenShift's API is configured with the Kubernetes API
Priority & Fairness feature enabled by default. This feature allows for
fine-grained configuration of the handling of incoming requests. [6]
This way it's possible to control how the cluster will react on an
overload situation. By default, OpenShift has a catch-all configuration
that classifies every request.

Finally, regardless of the environment that OpenShift is deployed in,
it is assumed that there is a load balancer or load balancing service
handling requests for the OpenShift API. This provides redundancy and
extra protection when dealing with Denial of Service attacks.

[1] https://docs.openshift.com/container-platform/4.7/nodes/clusters/nodes-cluster-overcommit.html
[2] https://docs.openshift.com/container-platform/4.7/applications/quotas/quotas-setting-per-project.html
[3] https://docs.openshift.com/container-platform/4.7/applications/quotas/quotas-setting-across-multiple-projects.html
[4] https://docs.openshift.com/container-platform/4.7/nodes/pods/nodes-pods-configuring.html#nodes-pods-configuring-bandwidth_nodes-pods-configuring
[5] https://docs.openshift.com/container-platform/4.7/networking/routes/route-configuration.html#nw-route-specific-annotations_route-configuration
[6] https://kubernetes.io/docs/concepts/cluster-administration/flow-control/

https://issues.redhat.com/browse/CMP-427

#### Rules:

  - routes_rate_limit
  - resource_requests_quota

#### Implementation Status: implemented

______________________________________________________________________
