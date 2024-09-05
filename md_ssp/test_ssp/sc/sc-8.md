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
    - name: routes_protected_by_tls
      description: OpenShift Container Platform provides methods for communicating
        from outside the cluster with services running in the cluster. TLS must be
        used to protect these communications. OpenShift Routes provide the ability
        to configure the needed TLS settings. With these, one is able to configure
        that any request coming from the outside must use TLS. To verify this, ensure
        that every Route in the system has a policy of Disable or Redirect to ensure
        a secure endpoint is used. The aforementioned policy will be set in a Routes
        .spec.tls.insecureEdgeTerminationPolicy setting.
    - name: api_server_https_for_kubelet_conn
      description: The kube-apiserver ensures https to the kubelet by default. The
        apiserver flag "--kubelet-https" is deprecated and should be either set to
        "true" or omitted from the argument list.
    - name: etcd_peer_auto_tls
      description: 'To ensure the etcd service is not using self-signed certificates,
        run the following command: $ oc get cm/etcd-pod -n openshift-etcd -o yaml
        The etcd pod configuration contained in the configmap should not contain the
        --peer-auto-tls=true flag.'
    - name: api_server_kubelet_certificate_authority
      description: 'To ensure OpenShift verifies kubelet certificates before establishing
        connections, follow the OpenShift documentation and setup the TLS connection
        between the API Server and kubelets. Edit the openshift-kube-apiserver configmap
        and set the below parameter if it is not already configured: "apiServerArguments":{
        ... "kubelet-certificate-authority":"/etc/kubernetes/static-pod-resources/configmaps/kubelet-serving-ca/ca-bundle.crt",
        ...'
    - name: controller_secure_port
      description: 'To ensure the Controller Manager service is bound to secure loopback
        address using a secure port, set the RotateKubeletServerCertificate option
        to true in the openshift-kube-controller-manager configmap on the master node(s):
        "extendedArguments": { ... "secure-port": ["10257"], ...'
    - name: api_server_etcd_key
      description: 'To ensure etcd is configured to make use of TLS encryption for
        client communications, follow the OpenShift documentation and setup the TLS
        connection between the API Server and etcd. Then, verify that apiServerArguments
        has the etcd-keyfile configured in the openshift-kube-apiserver configmap
        to something similar to: ... "etcd-keyfile": [ "/etc/kubernetes/static-pod-resources/secrets/etcd-client/tls.key"
        ], ...'
    - name: controller_service_account_ca
      description: 'To ensure the API Server utilizes its own key pair, set the masterCA
        parameter to the public key file for service accounts in the openshift-kube-controller-manager
        configmap on the master node(s): "extendedArguments": { ... "root-ca-file":
        [ "/etc/kubernetes/static-pod-resources/configmaps/serviceaccount-ca/ca-bundle.crt"
        ], ...'
    - name: etcd_peer_client_cert_auth
      description: 'To ensure the etcd service is serving TLS to clients, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: oc get -nopenshift-etcd cm etcd-pod
        -oyaml | grep "\-\-peer-client-cert-auth=" the parameter should be set to
        true.'
    - name: controller_rotate_kubelet_server_certs
      description: 'To enforce kubelet server certificate rotation on the Controller
        Manager, set the RotateKubeletServerCertificate option to true in the openshift-kube-controller-manager
        configmap on the master node(s): "extendedArguments": { ... "feature-gates":
        [ ... "RotateKubeletServerCertificate=true", ... ... This feature gate is
        enabled by default as of Kubernetes 1.12.'
    - name: api_server_openshift_https_serving_cert
      description: By default, the OpenShift API Server uses TLS. HTTPS should be
        used for connections between openshift-apiserver and kube-apiserver. By default,
        the OpenShift OAuth API Server uses Intermediate profile which requires a
        minimum TLS version of 1.2.
    - name: controller_service_account_private_key
      description: 'To ensure the API Server utilizes its own key pair, set the privateKeyFile
        parameter to the public key file for service accounts in the openshift-kube-controller-manager
        configmap on the master node(s): "extendedArguments": { ... "service-account-private-key-file":
        [ "/etc/kubernetes/static-pod-resources/secrets/service-account-private-key/service-account.key"
        ], ...'
    - name: etcd_key_file
      description: 'To ensure the etcd service is serving TLS to clients, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: oc get -nopenshift-etcd cm etcd-pod
        -oyaml | grep "\-\-key-file=/etc/kubernetes/static-pod-certs/secrets/etcd-all-[a-z]+/etcd-serving-NODE_NAME.key".
        Note that the [a-z]+ is being used since the directory might change between
        OpenShift versions.'
    - name: etcd_cert_file
      description: 'To ensure the etcd service is serving TLS to clients, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: --cert-file=/etc/kubernetes/static-pod-certs/secrets/etcd-all-[a-z]+/etcd-serving-NODE_NAME.crt.
        Note that the [a-z]+ is being used since the directory might change between
        OpenShift versions.'
    - name: api_server_kubelet_client_cert
      description: 'To enable certificate based kubelet authentication, edit the config
        configmap in the openshift-kube-apiserver namespace and set the below parameter
        in the config.yaml key if it is not already configured: "apiServerArguments":{
        ... "kubelet-client-certificate":"/etc/kubernetes/static-pod-resources/secrets/kubelet-client/tls.crt",
        ... }'
    - name: api_server_kubelet_client_cert_pre_4_9
      description: 'To enable certificate based kubelet authentication, edit the config
        configmap in the openshift-kube-apiserver namespace and set the below parameter
        in the config.yaml key if it is not already configured: "apiServerArguments":{
        ... "kubelet-client-certificate":"/etc/kubernetes/static-pod-resources/secrets/kubelet-client/tls.crt",
        ... } Note that this particular rule is only valid for OCP releases up to
        and including 4.8'
    - name: api_server_kubelet_client_key
      description: 'To enable certificate based kubelet authentication, edit the config
        configmap in the openshift-kube-apiserver namespace and set the below parameter
        in the config.yaml key if it is not already configured: "apiServerArguments":{
        ... "kubelet-client-key":"/etc/kubernetes/static-pod-resources/secrets/kubelet-client/tls.key",
        ... }'
    - name: api_server_kubelet_client_key_pre_4_9
      description: 'To enable certificate based kubelet authentication, edit the config
        configmap in the openshift-kube-apiserver namespace and set the below parameter
        in the config.yaml key if it is not already configured: "apiServerArguments":{
        ... "kubelet-client-key":"/etc/kubernetes/static-pod-resources/secrets/kubelet-client/tls.key",
        ... } Note that this particular rule is only valid for OCP releases up to
        and including 4.8'
    - name: api_server_etcd_cert
      description: 'To ensure etcd is configured to make use of TLS encryption for
        client communications, follow the OpenShift documentation and setup the TLS
        connection between the API Server and etcd. Then, verify that apiServerArguments
        has the etcd-certfile configured in the openshift-kube-apiserver configmap
        to something similar to: ... "etcd-certfile": [ "/etc/kubernetes/static-pod-resources/secrets/etcd-client/tls.crt"
        ], ...'
    - name: etcd_client_cert_auth
      description: 'To ensure the etcd service is serving TLS to clients, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: oc get -nopenshift-etcd cm etcd-pod
        -oyaml | grep "\-\-client-cert-auth=" the parameter should be set to true.'
    - name: controller_insecure_port_disabled
      description: 'To ensure the Controller Manager service is bound to secure loopback
        address and a secure port, set the RotateKubeletServerCertificate option to
        true in the openshift-kube-controller-manager configmap on the master node(s):
        "extendedArguments": { ... "port": ["0"], ... It is also acceptable for a
        system to deprecate the insecure port: "extendedArguments": { ... ...'
    - name: api_server_oauth_https_serving_cert
      description: By default, the OpenShift OAuth API Server uses TLS. HTTPS should
        be used for connections between openshift-oauth-apiserver and kube-apiserver.
        By default, the OpenShift OAuth API Server uses Intermediate profile which
        requires a minimum TLS version of 1.2.
    - name: etcd_auto_tls
      description: 'To ensure the etcd service is not using self-signed certificates,
        run the following command: $ oc get cm/etcd-pod -n openshift-etcd -o yaml
        The etcd pod configuration contained in the configmap should not contain the
        --auto-tls=true flag.'
    - name: ocp_no_ldap_insecure
      description: For users to interact with OpenShift Container Platform, they must
        first authenticate to the cluster. The authentication layer identifies the
        user associated with requests to the OpenShift Container Platform API. The
        authorization layer then uses information about the requesting user to determine
        if the request is allowed. Understanding authentication | Authentication |
        OpenShift Container Platform The OpenShift Container Platform includes a built-in
        OAuth server for token-based authentication. Developers and administrators
        obtain OAuth access tokens to authenticate themselves to the API. It is recommended
        for an administrator to configure OAuth to specify an identity provider after
        the cluster is installed. User access to the cluster is managed through the
        identity provider. Understanding identity provider configuration | Authentication
        | OpenShift Container Platform If the identity provider is LDAP, setting the
        insecure flag to true would mean that passwords, such as the one used to authenticate
        the OAuth proxy to the LDAP server would be transmitted in the clear, potentially
        allowing an attacker to read the password if they captured the network traffic.
    - name: etcd_peer_key_file
      description: 'To ensure the etcd service is serving TLS to peers, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: oc get -nopenshift-etcd cm etcd-pod
        -oyaml | grep "\-\-peer-key-file=/etc/kubernetes/static-pod-certs/secrets/etcd-all-[a-z]+/etcd-peer-NODE_NAME.key"
        Note that the [a-z]+ is being used since the directory might change between
        OpenShift versions.'
    - name: api_server_tls_private_key
      description: 'To ensure the API Server utilizes its own TLS certificates, the
        tls-private-key-file must be configured. Verify that the apiServerArguments
        section has the tls-private-key-file configured in the config configmap in
        the openshift-kube-apiserver namespace similar to: "apiServerArguments":{
        ... "tls-private-key-file": [ "/etc/kubernetes/static-pod-certs/secrets/service-network-serving-certkey/tls.key"
        ], ... }'
    - name: api_server_etcd_ca
      description: 'To ensure etcd is configured to make use of TLS encryption for
        client connections, follow the OpenShift documentation and setup the TLS connection
        between the API Server and etcd. Then, verify that apiServerArguments has
        the etcd-cafile configured in the openshift-kube-apiserver config configmap
        to something similar to: "apiServerArguments": { ... "etcd-cafile": [ "/etc/kubernetes/static-pod-resources/configmaps/etcd-serving-ca/ca-bundle.crt"
        ], ...'
    - name: api_server_client_ca
      description: 'Certificates must be provided to fully setup TLS client certificate
        authentication. To ensure the API Server utilizes its own TLS certificates,
        the clientCA must be configured. Verify that servingInfo has the clientCA
        configured in the openshift-kube-apiserver config configmap to something similar
        to: "apiServerArguments": { ... "client-ca-file": [ "/etc/kubernetes/static-pod-certs/configmaps/client-ca/ca-bundle.crt"
        ], ...'
    - name: api_server_tls_cert
      description: 'To ensure the API Server utilizes its own TLS certificates, the
        tls-cert-file must be configured. Verify that the apiServerArguments section
        has the tls-cert-file configured in the config configmap in the openshift-kube-apiserver
        namespace similar to: "apiServerArguments":{ ... "tls-cert-file": [ "/etc/kubernetes/static-pod-certs/secrets/service-network-serving-certkey/tls.crt"
        ], ... }'
    - name: kubelet_configure_tls_key
      description: 'To ensure the kubelet TLS private server key certificate is configured,
        edit the kubelet configuration file /etc/kubernetes/kubelet.conf and configure
        the kubelet private key file. tlsPrivateKeyFile: /path/to/TLS/private.key'
    - name: etcd_peer_cert_file
      description: 'To ensure the etcd service is serving TLS to peers, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: --peer-cert-file=/etc/kubernetes/static-pod-certs/secrets/etcd-all-[a-z]+/etcd-peer-NODE_NAME.crt
        Note that the [a-z]+ is being used since the directory might change between
        OpenShift versions.'
    - name: kubelet_configure_tls_cert
      description: 'To ensure the kubelet TLS client certificate is configured, edit
        the kubelet configuration file /etc/kubernetes/kubelet.conf and configure
        the kubelet certificate file. tlsCertFile: /path/to/TLS/cert.key'
    - name: kubelet_configure_tls_cert_pre_4_9
      description: 'To ensure the kubelet TLS client certificate is configured, edit
        the kubelet configuration file /etc/kubernetes/kubelet.conf and configure
        the kubelet certificate file. tlsCertFile: /path/to/TLS/cert.key Note that
        this particular rule is only valid for OCP releases up to and including 4.8'
    - name: api_server_tls_security_profile
      description: "The configuration tlsSecurityProfile specifies TLS configurations
        to be used while establishing connections with the externally exposed servers.
        Though secure transport mode is used for establishing connections, the protocols
        used may not always be strong enough to avoid interception and manipulation
        of the data in transport. TLS Security profile configured should not make
        use of any protocols, ciphers, and algorithms with known security vulnerabilities.
        tlsSecurityProfile can be configured to use one of custom, intermediate, modern,
        or old profile. Profile Old should be avoided at all times and when using
        custom profile one should be extremely careful as invalid configurations can
        be catastrophic. It is always advised to use highly secure intermediate or
        modern profiles and if unset a default is chosen. Update tlsSecurityProfile
        to Intermediate using the following command: oc patch apiservers.config.openshift.io
        cluster --type 'json' --patch '[{\"op\": \"add\", \"path\": \"/spec/tlsSecurityProfile/intermediate\"\
        , \"value\": {}}, {\"op\": \"replace\", \"path\": \"/spec/tlsSecurityProfile/type\"\
        , \"value\": \"Intermediate\"}' For more information, follow OpenShift documentation:
        the relevant documentation."
    - name: ingress_controller_tls_security_profile
      description: "The configuration tlsSecurityProfile specifies TLS configurations
        to be used while establishing connections with the externally exposed servers.
        Though secure transport mode is used for establishing connections, the protocols
        used may not always be strong enough to avoid interception and manipulation
        of the data in transport. TLS Security profile configured should not make
        use of any protocols, ciphers, and algorithms with known security vulnerabilities.
        tlsSecurityProfile can be configured to use one of custom, intermediate, modern,
        or old profile. Profile Old should be avoided at all times and when using
        custom profile one should be extremely careful as invalid configurations can
        be catastrophic. It is always advised to use highly secure intermediate or
        modern profiles and if unset profile configured in apiservers.config.openshift.io/cluster
        resource will be used as default. To update tlsSecurityProfile to Intermediate
        use the following command: oc patch -n openshift-ingress-operator ingresscontrollers.operator.openshift.io
        default --type 'json' --patch '[{\"op\": \"add\", \"path\": \"/spec/tlsSecurityProfile/intermediate\"\
        , \"value\": {}}, {\"op\": \"replace\", \"path\": \"/spec/tlsSecurityProfile/type\"\
        , \"value\": \"Intermediate\"}' For more information, follow OpenShift documentation:
        the relevant documentation."
    - name: kubelet_configure_tls_min_version
      description: 'The configuration tlsSecurityProfile specifies TLS configurations
        to be used while establishing connections with the externally exposed servers.
        Though secure transport mode is used for establishing connections, the protocols
        used may not always be strong enough to avoid interception and manipulation
        of the data in transport. TLS Security profile configured should not make
        use of any protocols, ciphers, and algorithms with known security vulnerabilities.
        tlsSecurityProfile can be configured to use one of custom, intermediate, modern,
        or old profile. Profile Old should be avoided at all times and when using
        custom profile one should be extremely careful as invalid configurations can
        be catastrophic. It is always advised to configure minimum TLS version to
        TLSv1.2 or latest when using Custom profile or to use predefined profiles
        Intermediate or modern. If a TLS security profile is not configured, the default
        TLS security profile is Intermediate. To configure Custom tlsSecurityProfile
        for the Kubelet with TLSv1.2 as minimum TLS version, create a new or modify
        existing KubeletConfig object along these lines, one for every MachineConfigPool:
        apiVersion: machineconfiguration.openshift.io/v1 kind: KubeletConfig metadata:
        name: kubelet-tls-config-$pool spec: tlsSecurityProfile: type: Custom custom:
        ciphers: - ECDHE-ECDSA-CHACHA20-POLY1305 - ECDHE-RSA-CHACHA20-POLY1305 - ECDHE-RSA-AES128-GCM-SHA256
        - ECDHE-ECDSA-AES128-GCM-SHA256 minTLSVersion: machineConfigPoolSelector:
        matchLabels: pools.operator.machineconfiguration.openshift.io/$pool_name:
        "" In order to configure this rule to check for an alternate TLS version,
        both var_kubelet_tls_min_version_regex and var_kubelet_tls_min_version should
        be updated. For more information, follow OpenShift documentation: the relevant
        documentation.'
x-trestle-rules-params:
  ocp4:
    - name: var_kubelet_tls_min_version_regex
      description: TLS versions available for configuring Kubelet, excluding insecure
        versions
      options: "{'default': '^(?!VersionTLS10|VersionTLS11)'}"
      rule-id: kubelet_configure_tls_min_version
x-trestle-comp-def-rules-param-vals:
  # You may set new values for rule parameters by adding
  #
  # ssp-values:
  #   - value 1
  #   - value 2
  #
  # below a section of values:
  # The values list refers to the values as set by the components, and the ssp-values are the new values
  # to be placed in SetParameters of the SSP.
  #
  ocp4:
    - name: var_kubelet_tls_min_version_regex
      values:
        - ^(?!VersionTLS10|VersionTLS11)
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
  sc-08_odp:
    alt-identifier: sc-8_prm_1
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
  sort-id: sc-08
---

# sc-8 - \[System and Communications Protection\] Transmission Confidentiality and Integrity

## Control Statement

Protect the [Selection (one or more): confidentiality; integrity] of transmitted information.

- \[sc-8_fr\]

## Control Assessment Objective

the [Selection (one or more): confidentiality; integrity] of transmitted information is/are protected.

## Control guidance

For each instance of data in transit, confidentiality AND integrity should be through cryptography as specified in SC-8 (1), physical means as specified in SC-8 (5), or in combination.

 

For clarity, this control applies to all data in transit. Examples include the following data flows:

* Crossing the system boundary
* Between compute instances - including containers
* From a compute instance to storage
* Replication between availability zones
* Transmission of backups to storage
* From a load balancer to a compute instance
* Flows from management tools required for their work - e.g. log collection, scanning, etc.


 

The following applies only when choosing SC-8 (5) in lieu of SC-8 (1).

FedRAMP-Defined Assignment / Selection Parameters 

SC-8 (5)-1 [a hardened or alarmed carrier Protective Distribution System (PDS) when outside of Controlled Access Area (CAA)]

SC-8 (5)-2 [prevent unauthorized disclosure of information AND detect changes to information]

SC-8 (5) applies when physical protection has been selected as the method to protect confidentiality and integrity. For physical protection, data in transit must be in either a Controlled Access Area (CAA), or a Hardened or alarmed PDS.

 

Hardened or alarmed PDS: Shall be as defined in SECTION X - CATEGORY 2 PDS INSTALLATION GUIDANCE of CNSSI No.7003, titled PROTECTED DISTRIBUTION SYSTEMS (PDS). Per the CNSSI No. 7003 Section VIII, PDS must originate and terminate in a Controlled Access Area (CAA).

 

Controlled Access Area (CAA): Data will be considered physically protected, and in a CAA if it meets Section 2.3 of the DHS's Recommended Practice: Improving Industrial Control System Cybersecurity with Defense-in-Depth Strategies. CSPs can meet Section 2.3 of the DHS' recommended practice by satisfactory implementation of the following controls PE-2 (1), PE-2 (2), PE-2 (3), PE-3 (2), PE-3 (3), PE-6 (2), and PE-6 (3).

 

Note: When selecting SC-8 (5), the above SC-8(5), and the above referenced PE controls must be added to the SSP.

 

CNSSI No.7003 can be accessed here:

https://www.dcsa.mil/Portals/91/documents/ctp/nao/CNSSI_7003_PDS_September_2015.pdf

 

DHS Recommended Practice: Improving Industrial Control System Cybersecurity with Defense-in-Depth Strategies can be accessed here:

https://us-cert.cisa.gov/sites/default/files/FactSheets/NCCIC%20ICS_FactSheet_Defense_in_Depth_Strategies_S508C.pdf

Protecting the confidentiality and integrity of transmitted information applies to internal and external networks as well as any system components that can transmit information, including servers, notebook computers, desktop computers, mobile devices, printers, copiers, scanners, facsimile machines, and radios. Unprotected communication paths are exposed to the possibility of interception and modification. Protecting the confidentiality and integrity of information can be accomplished by physical or logical means. Physical protection can be achieved by using protected distribution systems. A protected distribution system is a wireline or fiber-optics telecommunications system that includes terminals and adequate electromagnetic, acoustical, electrical, and physical controls to permit its use for the unencrypted transmission of classified information. Logical protection can be achieved by employing encryption techniques.

Organizations that rely on commercial providers who offer transmission services as commodity services rather than as fully dedicated services may find it difficult to obtain the necessary assurances regarding the implementation of needed controls for transmission confidentiality and integrity. In such situations, organizations determine what types of confidentiality or integrity services are available in standard, commercial telecommunications service packages. If it is not feasible to obtain the necessary controls and assurances of control effectiveness through appropriate contracting vehicles, organizations can implement appropriate compensating controls.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: sc-8 -->

#### Implementation Status: planned

### ocp4

The customer will be responsible for configuring TLS for transmitted
information.

#### Rules:

  - etcd_peer_key_file
  - api_server_etcd_cert
  - controller_service_account_private_key
  - etcd_client_cert_auth
  - controller_insecure_port_disabled
  - etcd_key_file
  - api_server_https_for_kubelet_conn
  - api_server_tls_private_key
  - api_server_oauth_https_serving_cert
  - controller_service_account_ca
  - api_server_etcd_ca
  - api_server_client_ca
  - api_server_tls_cert
  - etcd_peer_auto_tls
  - routes_protected_by_tls
  - ocp_no_ldap_insecure
  - etcd_cert_file
  - api_server_kubelet_certificate_authority
  - etcd_auto_tls
  - api_server_kubelet_client_cert
  - api_server_kubelet_client_cert_pre_4_9
  - kubelet_configure_tls_key
  - etcd_peer_client_cert_auth
  - controller_secure_port
  - etcd_peer_cert_file
  - controller_rotate_kubelet_server_certs
  - api_server_openshift_https_serving_cert
  - api_server_etcd_key
  - kubelet_configure_tls_cert
  - kubelet_configure_tls_cert_pre_4_9
  - api_server_kubelet_client_key
  - api_server_kubelet_client_key_pre_4_9
  - api_server_tls_security_profile
  - ingress_controller_tls_security_profile
  - kubelet_configure_tls_min_version

#### Implementation Status: implemented

______________________________________________________________________
