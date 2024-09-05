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
    - name: configure_network_policies_namespaces
      description: Use network policies to isolate traffic in your cluster network.
    - name: directory_permissions_var_log_oauth_audit
      description: 'To properly set the permissions of /var/log/oauth-apiserver/,
        run the command: $ sudo chmod 0700 /var/log/oauth-apiserver/'
    - name: file_ownership_var_log_oauth_audit
      description: 'All audit logs must be owned by root user and group. By default,
        the path for the OAuth audit log is /var/log/oauth-apiserver/. To properly
        set the owner of /var/log/oauth-apiserver, run the command: $ sudo chown root
        /var/log/oauth-apiserver To properly set the owner of /var/log/oauth-apiserver/*,
        run the command: $ sudo chown root /var/log/oauth-apiserver/*'
    - name: file_ownership_var_log_kube_audit
      description: 'All audit logs must be owned by root user and group. By default,
        the path for the Kubernetes audit log is /var/log/kube-apiserver/. To properly
        set the owner of /var/log/kube-apiserver, run the command: $ sudo chown root
        /var/log/kube-apiserver To properly set the owner of /var/log/kube-apiserver/*,
        run the command: $ sudo chown root /var/log/kube-apiserver/*'
    - name: file_permissions_var_log_ocp_audit
      description: 'To properly set the permissions of /var/log/openshift-apiserver/.*,
        run the command: $ sudo chmod 0600 /var/log/openshift-apiserver/.*'
    - name: directory_permissions_var_log_kube_audit
      description: 'To properly set the permissions of /var/log/kube-apiserver/, run
        the command: $ sudo chmod 0700 /var/log/kube-apiserver/'
    - name: file_permissions_var_log_kube_audit
      description: 'To properly set the permissions of /var/log/kube-apiserver/.*,
        run the command: $ sudo chmod 0600 /var/log/kube-apiserver/.*'
    - name: file_permissions_var_log_oauth_audit
      description: 'To properly set the permissions of /var/log/oauth-apiserver/.*,
        run the command: $ sudo chmod 0600 /var/log/oauth-apiserver/.*'
    - name: file_ownership_var_log_ocp_audit
      description: 'All audit logs must be owned by root user and group. By default,
        the path for the OpenShift audit log is /var/log/openshift-apiserver/. To
        properly set the owner of /var/log/openshift-apiserver, run the command: $
        sudo chown root /var/log/openshift-apiserver To properly set the owner of
        /var/log/openshift-apiserver/*, run the command: $ sudo chown root /var/log/openshift-apiserver/*'
    - name: directory_permissions_var_log_ocp_audit
      description: 'To properly set the permissions of /var/log/openshift-apiserver/,
        run the command: $ sudo chmod 0700 /var/log/openshift-apiserver/'
    - name: directory_access_var_log_kube_audit
      description: The audit system should collect access events to read the Kubernetes
        audit log directory. The following audit rule will assure that access to audit
        log directory are collected. -a always,exit -F dir=/var/log/kube-apiserver/
        -F perm=r -F auid>=1000 -F auid!=unset -F key=access-audit-trail If the auditd
        daemon is configured to use the augenrules program to read audit rules during
        daemon startup (the default), add the rule to a file with suffix .rules in
        the directory /etc/audit/rules.d. If the auditd daemon is configured to use
        the auditctl utility to read audit rules during daemon startup, add the rule
        to /etc/audit/audit.rules file.
    - name: directory_access_var_log_oauth_audit
      description: The audit system should collect access events to read the OAuth
        audit log directory. The following audit rule will assure that access to audit
        log directory are collected. -a always,exit -F dir=/var/log/oauth-apiserver/
        -F perm=r -F auid>=1000 -F auid!=unset -F key=access-audit-trail If the auditd
        daemon is configured to use the augenrules program to read audit rules during
        daemon startup (the default), add the rule to a file with suffix .rules in
        the directory /etc/audit/rules.d. If the auditd daemon is configured to use
        the auditctl utility to read audit rules during daemon startup, add the rule
        to /etc/audit/audit.rules file.
    - name: directory_access_var_log_ocp_audit
      description: The audit system should collect access events to read the OpenShift
        audit log directory. The following audit rule will assure that access to audit
        log directory are collected. -a always,exit -F dir=/var/log/openshift-apiserver/
        -F perm=r -F auid>=1000 -F auid!=unset -F key=access-audit-trail If the auditd
        daemon is configured to use the augenrules program to read audit rules during
        daemon startup (the default), add the rule to a file with suffix .rules in
        the directory /etc/audit/rules.d. If the auditd daemon is configured to use
        the auditctl utility to read audit rules during daemon startup, add the rule
        to /etc/audit/audit.rules file.
    - name: file_perms_openshift_sdn_cniserver_config
      description: 'To properly set the permissions of /var/run/openshift-sdn/cniserver/config.json,
        run the command: $ sudo chmod 0444 /var/run/openshift-sdn/cniserver/config.json'
    - name: file_owner_openshift_sdn_cniserver_config
      description: 'To properly set the owner of /var/run/openshift-sdn/cniserver/config.json,
        run the command: $ sudo chown root /var/run/openshift-sdn/cniserver/config.json'
    - name: api_server_admission_control_plugin_namespacelifecycle
      description: OpenShift enables the NamespaceLifecycle plugin by default.
    - name: api_server_request_timeout
      description: 'The API server minimum request timeout defines the minimum number
        of seconds a handler must keep a request open before timing it out. To set
        this, edit the openshift-kube-apiserver configmap and set min-request-timeout
        under the apiServerArguments field: "apiServerArguments":{ ... "min-request-timeout":[
        ], ...'
    - name: file_permissions_openshift_pki_key_files
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/*/*/*/*.key,
        run the command: $ sudo chmod 0600 /etc/kubernetes/static-pod-resources/*/*/*/*.key'
    - name: file_owner_cni_conf
      description: 'To properly set the owner of /etc/cni/net.d/*, run the command:
        $ sudo chown root /etc/cni/net.d/*'
    - name: ocp_api_server_audit_log_maxsize
      description: 'To rotate audit logs upon reaching a maximum size, edit the openshift-apiserver
        configmap and set the audit-log-maxsize parameter to an appropriate size in
        MB. For example, to set it to 100 MB: "apiServerArguments":{ ... "audit-log-maxsize":
        ["100"], ...'
    - name: file_owner_master_admin_kubeconfigs
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/kube-apiserver-certs/secrets/node-kubeconfigs/*.kubeconfig,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/kube-apiserver-certs/secrets/node-kubeconfigs/*.kubeconfig'
    - name: file_permissions_ovsdb_server_pid
      description: 'To properly set the permissions of /run/openvswitch/ovsdb-server.pid,
        run the command: $ sudo chmod 0644 /run/openvswitch/ovsdb-server.pid'
    - name: file_groupowner_kube_scheduler
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/kube-scheduler-pod.yaml,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/kube-scheduler-pod.yaml'
    - name: file_groupowner_etcd_member
      description: 'To properly set the group owner of /etc/kubernetes/manifests/etcd-pod.yaml,
        run the command: $ sudo chgrp root /etc/kubernetes/manifests/etcd-pod.yaml'
    - name: file_permissions_openshift_pki_cert_files
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/kube-*/secrets/*/tls.crt,
        run the command: $ sudo chmod 0600 /etc/kubernetes/static-pod-resources/kube-*/secrets/*/tls.crt'
    - name: kubelet_enable_server_cert_rotation
      description: 'To enable the kubelet to rotate server certificates, edit the
        kubelet configuration file /etc/kubernetes/kubelet.conf on the kubelet node(s)
        and set the below parameter: serverTLSBootstrap: true'
    - name: file_permissions_ovs_conf_db_lock
      description: 'To properly set the permissions of /etc/openvswitch/.conf.db.~lock~,
        run the command: $ sudo chmod 0600 /etc/openvswitch/.conf.db.~lock~'
    - name: rbac_limit_secrets_access
      description: The Kubernetes API stores secrets, which may be service account
        tokens for the Kubernetes API or credentials used by workloads in the cluster.
        Access to these secrets should be restricted to the smallest possible group
        of users to reduce the risk of privilege escalation. To restrict users from
        secrets, remove get, list, and watch access to unauthorized users to secret
        objects in the cluster.
    - name: file_permissions_worker_service
      description: 'To properly set the permissions of /etc/systemd/system/kubelet.service,
        run the command: $ sudo chmod 0644 /etc/systemd/system/kubelet.service'
    - name: api_server_bind_address
      description: The bindAddress is set by default to 0.0.0.0:6443, and listening
        with TLS enabled.
    - name: api_server_audit_log_path
      description: 'To enable auditing on the Kubernetes API Server, the audit log
        path must be set. Edit the openshift-kube-apiserver configmap and set the
        audit-log-path to a suitable path and file where audit logs should be written.
        For example: "apiServerArguments":{ ... "audit-log-path":"/var/log/kube-apiserver/audit.log",
        ...'
    - name: file_permissions_kubelet_conf
      description: 'To properly set the permissions of /etc/kubernetes/kubelet.conf,
        run the command: $ sudo chmod 0644 /etc/kubernetes/kubelet.conf'
    - name: file_permissions_kubelet
      description: 'To properly set the permissions of /var/lib/kubelet/config.json,
        run the command: $ sudo chmod 0600 /var/lib/kubelet/config.json'
    - name: api_server_https_for_kubelet_conn
      description: The kube-apiserver ensures https to the kubelet by default. The
        apiserver flag "--kubelet-https" is deprecated and should be either set to
        "true" or omitted from the argument list.
    - name: file_owner_ovs_vswitchd_pid
      description: 'To properly set the owner of /run/openvswitch/ovs-vswitchd.pid,
        run the command: $ sudo chown openvswitch /run/openvswitch/ovs-vswitchd.pid'
    - name: api_server_audit_log_maxbackup
      description: 'To configure how many rotations of audit logs are retained, edit
        the openshift-kube-apiserver configmap and set the audit-log-maxbackup parameter
        to 10 or to an organizationally appropriate value: "apiServerArguments":{
        ... "audit-log-maxbackup": [10], ...'
    - name: file_owner_ovs_conf_db_lock
      description: 'To properly set the owner of /etc/openvswitch/.conf.db.~lock~,
        run the command: $ sudo chown openvswitch /etc/openvswitch/.conf.db.~lock~'
    - name: file_owner_scheduler_kubeconfig
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/configmaps/scheduler-kubeconfig/kubeconfig,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/configmaps/scheduler-kubeconfig/kubeconfig'
    - name: file_permissions_multus_conf
      description: 'To properly set the permissions of /var/run/multus/cni/net.d/*,
        run the command: $ sudo chmod 0644 /var/run/multus/cni/net.d/*'
    - name: ocp_api_server_audit_log_maxbackup
      description: 'To configure how many rotations of audit logs are retained, edit
        the openshift-apiserver configmap and set the audit-log-maxbackup parameter
        to 10 or to an organizationally appropriate value: "apiServerArguments":{
        ... "audit-log-maxbackup": [10], ...'
    - name: etcd_peer_auto_tls
      description: 'To ensure the etcd service is not using self-signed certificates,
        run the following command: $ oc get cm/etcd-pod -n openshift-etcd -o yaml
        The etcd pod configuration contained in the configmap should not contain the
        --peer-auto-tls=true flag.'
    - name: file_groupowner_worker_kubeconfig
      description: 'To properly set the group owner of /var/lib/kubelet/kubeconfig,
        run the command: $ sudo chgrp root /var/lib/kubelet/kubeconfig'
    - name: file_permissions_kube_controller_manager
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/kube-controller-manager-pod.yaml,
        run the command: $ sudo chmod 0600 /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/kube-controller-manager-pod.yaml'
    - name: kubelet_eviction_thresholds_set_hard_nodefs_available
      description: 'Two types of garbage collection are performed on an OpenShift
        Container Platform node: Container garbage collection: Removes terminated
        containers. Image garbage collection: Removes images not referenced by any
        running pods. Container garbage collection can be performed using eviction
        thresholds. Image garbage collection relies on disk usage as reported by cAdvisor
        on the node to decide which images to remove from the node. The OpenShift
        administrator can configure how OpenShift Container Platform performs garbage
        collection by creating a kubeletConfig object for each Machine Config Pool
        using any combination of the following: soft eviction for containers hard
        eviction for containers eviction for images To configure, follow the directions
        in the documentation This rule pertains to the nodefs.available setting of
        the evictionHard section. Remediation will set field nodefs.available to {{
        .var_kubelet_evictionhard_nodefs_available }} based on the variable var_kubelet_evictionhard_nodefs_available.'
    - name: file_groupowner_kube_apiserver
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/kube-apiserver-pod-*/kube-apiserver-pod.yaml,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/kube-apiserver-pod-*/kube-apiserver-pod.yaml'
    - name: file_owner_kube_scheduler
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/kube-scheduler-pod.yaml,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/kube-scheduler-pod.yaml'
    - name: accounts_restrict_service_account_tokens
      description: Service accounts tokens should not be mounted in pods except where
        the workload running in the pod explicitly needs to communicate with the API
        server. To ensure pods do not automatically mount tokens, set automountServiceAccountToken
        to false.
    - name: file_groupowner_ovs_vswitchd_pid
      description: Ensure that the file /run/openvswitch/ovs-vswitchd.pid, is owned
        by the group openvswitch or hugetlbfs, depending on your settings and Open
        vSwitch version.
    - name: scc_limit_ipc_namespace
      description: Containers should not be allowed access to the host's Interprocess
        Communication (IPC) namespace. To prevent containers from getting access to
        a host's IPC namespace, the appropriate Security Context Constraints (SCCs)
        should set allowHostIPC to false.
    - name: api_server_kubelet_certificate_authority
      description: 'To ensure OpenShift verifies kubelet certificates before establishing
        connections, follow the OpenShift documentation and setup the TLS connection
        between the API Server and kubelets. Edit the openshift-kube-apiserver configmap
        and set the below parameter if it is not already configured: "apiServerArguments":{
        ... "kubelet-certificate-authority":"/etc/kubernetes/static-pod-resources/configmaps/kubelet-serving-ca/ca-bundle.crt",
        ...'
    - name: scc_limit_privileged_containers
      description: Containers should be limited to only the privileges required to
        run. To prevent containers from running as privileged containers, the appropriate
        Security Context Constraints (SCCs) should set allowPrivilegedContainer to
        false.
    - name: file_groupowner_openshift_pki_key_files
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/*/*/*/*.key,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/*/*/*/*.key'
    - name: controller_secure_port
      description: 'To ensure the Controller Manager service is bound to secure loopback
        address using a secure port, set the RotateKubeletServerCertificate option
        to true in the openshift-kube-controller-manager configmap on the master node(s):
        "extendedArguments": { ... "secure-port": ["10257"], ...'
    - name: api_server_service_account_public_key
      description: 'To ensure the API Server utilizes its own key pair, edit the openshift-kube-apiserver
        configmap and set the serviceAccountPublicKeyFiles parameter to the public
        key file for service accounts: ... "serviceAccountPublicKeyFiles":[ "/etc/kubernetes/static-pod-resources/configmaps/sa-token-signing-certs"
        ], ...'
    - name: secrets_no_environment_variables
      description: Secrets should be mounted as data volumes instead of environment
        variables.
    - name: api_server_admission_control_plugin_noderestriction
      description: "To limit the Node and Pod objects that a kubelet could modify,
        ensure that the NodeRestriction plugin on kubelets is enabled in the api-server
        configuration by running the following command: $ oc -n openshift-kube-apiserver
        get configmap config -o json | jq -r '.data.\"config.yaml\"' | jq '.apiServerArguments.\"\
        enable-admission-plugins\"'"
    - name: kubelet_configure_client_ca
      description: 'By default, the kubelet is not configured with a CA certificate
        which can subject the kubelet to man-in-the-middle attacks. To configure a
        client CA certificate, edit the kubelet configuration file /etc/kubernetes/kubelet.conf
        on the kubelet node(s) and set the below parameter: authentication: ... x509:
        clientCAFile: /etc/kubernetes/kubelet-ca.crt ...'
    - name: file_owner_ovs_sys_id_conf
      description: 'To properly set the owner of /etc/openvswitch/system-id.conf,
        run the command: $ sudo chown openvswitch /etc/openvswitch/system-id.conf'
    - name: file_permissions_cni_conf
      description: 'To properly set the permissions of /etc/cni/net.d/*, run the command:
        $ sudo chmod 0600 /etc/cni/net.d/*'
    - name: file_groupowner_worker_service
      description: "' To properly set the group owner of /etc/systemd/system/kubelet.service,
        run the command: $ sudo chgrp root /etc/systemd/system/kubelet.service'"
    - name: file_owner_etcd_data_dir
      description: 'To properly set the owner of /var/lib/etcd/member/, run the command:
        $ sudo chown root /var/lib/etcd/member/'
    - name: file_groupowner_controller_manager_kubeconfig
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/configmaps/controller-manager-kubeconfig/kubeconfig,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/configmaps/controller-manager-kubeconfig/kubeconfig'
    - name: api_server_api_priority_flowschema_catch_all
      description: 'Using APIPriorityAndFairness feature provides a fine-grained way
        to control the behaviour of the Kubernetes API server in an overload situation.
        The well-known FlowSchema catch-all should be available to make sure that
        every request gets some kind of classification. By default, the catch-all
        priority level only allows one concurrency share and does not queue requests.
        To inspect all the FlowSchema objects, run: oc get flowschema To inspect the
        well-known catch-all object, run the following: oc describe flowschema catch-all'
    - name: api_server_audit_log_maxsize
      description: 'To rotate audit logs upon reaching a maximum size, edit the openshift-kube-apiserver
        configmap and set the audit-log-maxsize parameter to an appropriate size in
        MB. For example, to set it to 100 MB: "apiServerArguments":{ ... "audit-log-maxsize":
        ["100"], ...'
    - name: file_permissions_etcd_data_dir
      description: 'To properly set the permissions of /var/lib/etcd, run the command:
        $ sudo chmod 0700 /var/lib/etcd'
    - name: api_server_etcd_key
      description: 'To ensure etcd is configured to make use of TLS encryption for
        client communications, follow the OpenShift documentation and setup the TLS
        connection between the API Server and etcd. Then, verify that apiServerArguments
        has the etcd-keyfile configured in the openshift-kube-apiserver configmap
        to something similar to: ... "etcd-keyfile": [ "/etc/kubernetes/static-pod-resources/secrets/etcd-client/tls.key"
        ], ...'
    - name: general_default_namespace_use
      description: Kubernetes provides a default namespace, where objects are placed
        if no namespace is specified for them. Placing objects in this namespace makes
        application of RBAC and other controls more difficult.
    - name: scc_limit_privilege_escalation
      description: Containers should be limited to only the privileges required to
        run and should not be allowed to escalate their privileges. To prevent containers
        from escalating privileges, the appropriate Security Context Constraints (SCCs)
        should set allowPrivilegeEscalation to false.
    - name: rbac_pod_creation_access
      description: The ability to create pods in a namespace can provide a number
        of opportunities for privilege escalation. Where applicable, remove create
        access to pod objects in the cluster.
    - name: file_groupowner_worker_ca
      description: 'To properly set the group owner of /etc/kubernetes/kubelet-ca.crt,
        run the command: $ sudo chgrp root /etc/kubernetes/kubelet-ca.crt'
    - name: api_server_auth_mode_no_aa
      description: Do not always authorize all requests.
    - name: file_permissions_ovs_pid
      description: 'To properly set the permissions of /var/run/openvswitch/ovs-vswitchd.pid,
        run the command: $ sudo chmod 0644 /var/run/openvswitch/ovs-vswitchd.pid'
    - name: file_groupowner_ovsdb_server_pid
      description: Ensure that the file /run/openvswitch/ovsdb-server.pid, is owned
        by the group openvswitch or hugetlbfs, depending on your settings and Open
        vSwitch version.
    - name: file_groupowner_ip_allocations
      description: 'To properly set the group owner of /var/lib/cni/networks/openshift-sdn/.*,
        run the command: $ sudo chgrp root /var/lib/cni/networks/openshift-sdn/.*'
    - name: file_permissions_ovs_conf_db
      description: 'To properly set the permissions of /etc/openvswitch/conf.db, run
        the command: $ sudo chmod 0640 /etc/openvswitch/conf.db'
    - name: kubelet_eviction_thresholds_set_hard_memory_available
      description: 'Two types of garbage collection are performed on an OpenShift
        Container Platform node: Container garbage collection: Removes terminated
        containers. Image garbage collection: Removes images not referenced by any
        running pods. Container garbage collection can be performed using eviction
        thresholds. Image garbage collection relies on disk usage as reported by cAdvisor
        on the node to decide which images to remove from the node. The OpenShift
        administrator can configure how OpenShift Container Platform performs garbage
        collection by creating a kubeletConfig object for each Machine Config Pool
        using any combination of the following: soft eviction for containers hard
        eviction for containers eviction for images To configure, follow the directions
        in the documentation This rule pertains to the memory.available setting of
        the evictionHard section. Remediation will set field memory.available to {{
        .var_kubelet_evictionhard_memory_available }} based on the variable var_kubelet_evictionhard_memory_available.'
    - name: api_server_token_auth
      description: 'To ensure OpenShift does not accept token-based authentication,
        follow the OpenShift documentation and configure alternate mechanisms for
        authentication. Then, edit the API Server pod specification file Edit the
        openshift-kube-apiserver configmap and remove the token-auth-file parameter:
        "apiServerArguments":{ ... "token-auth-file":[ "/path/to/any/file" ], ...'
    - name: file_owner_worker_kubeconfig
      description: 'To properly set the owner of /var/lib/kubelet/kubeconfig, run
        the command: $ sudo chown root /var/lib/kubelet/kubeconfig'
    - name: file_permissions_controller_manager_kubeconfig
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/configmaps/controller-manager-kubeconfig/kubeconfig,
        run the command: $ sudo chmod 0600 /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/configmaps/controller-manager-kubeconfig/kubeconfig'
    - name: controller_service_account_ca
      description: 'To ensure the API Server utilizes its own key pair, set the masterCA
        parameter to the public key file for service accounts in the openshift-kube-controller-manager
        configmap on the master node(s): "extendedArguments": { ... "root-ca-file":
        [ "/etc/kubernetes/static-pod-resources/configmaps/serviceaccount-ca/ca-bundle.crt"
        ], ...'
    - name: file_permissions_worker_ca
      description: 'To properly set the permissions of /etc/kubernetes/kubelet-ca.crt,
        run the command: $ sudo chmod 0644 /etc/kubernetes/kubelet-ca.crt'
    - name: kubelet_enable_streaming_connections
      description: 'Timouts for streaming connections should not be disabled as they
        help to prevent denial-of-service attacks. To configure streaming connection
        timeouts To set the streamingConnectionIdleTimeout option for the kubelet,
        create a KubeletConfig option along these lines: apiVersion: machineconfiguration.openshift.io/v1
        kind: KubeletConfig metadata: name: kubelet-config-$pool spec: machineConfigPoolSelector:
        matchLabels: pools.operator.machineconfiguration.openshift.io/$pool_name:
        "" kubeletConfig: streamingConnectionIdleTimeout:'
    - name: kubelet_authorization_mode
      description: 'Unauthenticated/unauthorized users should have no access to OpenShift
        nodes. The Kubelet should be set to only allow Webhook authorization. To ensure
        that the Kubelet requires authorization, validate that authorization is configured
        to Webhook in /etc/kubernetes/kubelet.conf: authorization: mode: Webhook ...'
    - name: etcd_unique_ca
      description: A unique CA certificate should be created for etcd. OpenShift by
        default creates separate PKIs for etcd and the Kubernetes API server. The
        same is done for other points of communication in the cluster.
    - name: file_owner_openshift_pki_cert_files
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/*/*/*/tls.crt,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/*/*/*/tls.crt'
    - name: kubelet_eviction_thresholds_set_hard_nodefs_inodesfree
      description: 'Two types of garbage collection are performed on an OpenShift
        Container Platform node: Container garbage collection: Removes terminated
        containers. Image garbage collection: Removes images not referenced by any
        running pods. Container garbage collection can be performed using eviction
        thresholds. Image garbage collection relies on disk usage as reported by cAdvisor
        on the node to decide which images to remove from the node. The OpenShift
        administrator can configure how OpenShift Container Platform performs garbage
        collection by creating a kubeletConfig object for each Machine Config Pool
        using any combination of the following: soft eviction for containers hard
        eviction for containers eviction for images To configure, follow the directions
        in the documentation This rule pertains to the nodefs.inodesFree setting of
        the evictionHard section. Remediation will set field nodefs.inodesFree to
        {{ .var_kubelet_evictionhard_nodefs_inodesfree }} based on the variable var_kubelet_evictionhard_nodefs_inodesfree.'
    - name: scc_limit_net_raw_capability
      description: Containers should not enable more capabilities than needed as this
        opens the door for malicious use. CAP_NET_RAW enables a container to launch
        a network attack on another container or cluster. To disable the CAP_NET_RAW
        capability, the appropriate Security Context Constraints (SCCs) should set
        NET_RAW in requiredDropCapabilities.
    - name: file_permissions_worker_kubeconfig
      description: 'To properly set the permissions of /var/lib/kubelet/kubeconfig,
        run the command: $ sudo chmod 0600 /var/lib/kubelet/kubeconfig'
    - name: scc_limit_root_containers
      description: Containers should run as a random non-privileged user. To prevent
        containers from running as root user, the appropriate Security Context Constraints
        (SCCs) should set .runAsUser.type to MustRunAsRange.
    - name: file_owner_openshift_pki_key_files
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/*/*/*/*.key,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/*/*/*/*.key'
    - name: etcd_peer_client_cert_auth
      description: 'To ensure the etcd service is serving TLS to clients, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: oc get -nopenshift-etcd cm etcd-pod
        -oyaml | grep "\-\-peer-client-cert-auth=" the parameter should be set to
        true.'
    - name: file_groupowner_master_admin_kubeconfigs
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/kube-apiserver-certs/secrets/node-kubeconfigs/*.kubeconfig,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/kube-apiserver-certs/secrets/node-kubeconfigs/*.kubeconfig'
    - name: file_integrity_exists
      description: The File Integrity Operator continually runs file integrity checks
        on the cluster nodes. It deploys a daemon set that initializes and runs privileged
        AIDE containers on each node, providing a status object with a log of files
        that are modified during the initial run of the daemon set pods.
    - name: file_owner_proxy_kubeconfig
      description: "To ensure the Kubernetes ConfigMap is mounted into the sdn daemonset
        pods with the correct ownership, make sure that the sdn-config ConfigMap is
        mounted using a ConfigMap at the /config mount point and that the sdn container
        points to that configuration using the --proxy-config command line option.
        Run: oc get -nopenshift-sdn ds sdn -ojson | jq -r '.spec.template.spec.containers[]
        | select(.name == \"sdn\")' and ensure the --proxy-config parameter points
        to /config/kube-proxy-config.yaml and that the config mount point is mounted
        from the sdn-config ConfigMap."
    - name: file_groupowner_etcd_data_files
      description: 'To properly set the group owner of /var/lib/etcd/member/wal/*,
        run the command: $ sudo chgrp root /var/lib/etcd/member/wal/*'
    - name: api_server_auth_mode_node
      description: Restrict kubelet nodes to reading only objects associated with
        them.
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
    - name: api_server_service_account_lookup
      description: Validate service account before validating token.
    - name: file_groupowner_openshift_pki_cert_files
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/*/*/*/tls.crt,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/*/*/*/tls.crt'
    - name: general_namespaces_in_use
      description: Use namespaces to isolate your Kubernetes objects.
    - name: file_groupowner_kubelet_conf
      description: 'To properly set the group owner of /etc/kubernetes/kubelet.conf,
        run the command: $ sudo chgrp root /etc/kubernetes/kubelet.conf'
    - name: accounts_unique_service_account
      description: 'Using the default service account prevents accurate application
        rights review and audit tracing. Instead of default, create a new and unique
        service account with the following command: $ oc create sa service_account_name
        where service_account_name is the name of a service account that is needed
        in the project namespace.'
    - name: api_server_admission_control_plugin_service_account
      description: "To ensure ServiceAccount objects must be created and granted before
        pod creation is allowed, follow the documentation and create ServiceAccount
        objects as per your environment. Ensure that the plugin is enabled in the
        api-server configuration: $ oc -n openshift-kube-apiserver get configmap config
        -o json | jq -r '.data.\"config.yaml\"' | jq '.apiServerArguments.\"enable-admission-plugins\"\
        '"
    - name: file_owner_kube_controller_manager
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/kube-controller-manager-pod.yaml,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/kube-controller-manager-pod.yaml'
    - name: kubelet_enable_protect_kernel_sysctl
      description: "Setup required tuned kernel parameters before enabling overwritten
        protection. Note that depending on the Linux distribution and its version
        that your cluster nodes are running, these parameters might be already set
        up for you. Please refer to the rule instructions for a check. Before enabling
        kernel parameter overwritten protection default, it's important to check if
        these values are already set to the required values. If not, it is necessary
        to first create a MachineConfig object that persist the required sysctl's.
        The required sysctl's are the following: kernel.keys.root_maxbytes=25000000
        kernel.keys.root_maxkeys=1000000 kernel.panic=10 kernel.panic_on_oops=1 vm.overcommit_memory=1
        vm.panic_on_oom=0 The these need to be enabled via MachineConfig since they
        need to be available as soon as the node starts and before the Kubelet does.
        The manifest may look as follows: --- apiVersion: machineconfiguration.openshift.io/v1
        kind: MachineConfig metadata: labels: machineconfiguration.openshift.io/role:
        master name: 75-master-kubelet-sysctls spec: config: ignition: version: 3.1.0
        storage: files: - contents: source: data:,vm.overcommit_memory%3D1%0Avm.panic_on_oom%3D0%0Akernel.panic%3D10%0Akernel.panic_on_oops%3D1%0Akernel.keys.root_maxkeys%3D1000000%0Akernel.keys.root_maxbytes%3D25000000%0A
        mode: 0644 path: /etc/sysctl.d/90-kubelet.conf overwrite: true This will need
        to be done for each relevant MachineConfigPool in the cluster. To configure,
        follow the directions in the documentation"
    - name: kubelet_enable_protect_kernel_defaults
      description: "Protect tuned kernel parameters from being overwritten by the
        kubelet. Before enabling this kernel parameter, it's important and necessary
        to first create a MachineConfig object that persist the required sysctl's.
        The required sysctl's are the following: kernel.keys.root_maxbytes=25000000
        kernel.keys.root_maxkeys=1000000 kernel.panic=10 kernel.panic_on_oops=1 vm.overcommit_memory=1
        vm.panic_on_oom=0 The these need to be enabled via MachineConfig since they
        need to be available as soon as the node starts and before the Kubelet does.
        The manifest may look as follows: --- apiVersion: machineconfiguration.openshift.io/v1
        kind: MachineConfig metadata: labels: machineconfiguration.openshift.io/role:
        master name: 75-master-kubelet-sysctls spec: config: ignition: version: 3.1.0
        storage: files: - contents: source: data:,vm.overcommit_memory%3D1%0Avm.panic_on_oom%3D0%0Akernel.panic%3D10%0Akernel.panic_on_oops%3D1%0Akernel.keys.root_maxkeys%3D1000000%0Akernel.keys.root_maxbytes%3D25000000%0A
        mode: 0644 path: /etc/sysctl.d/90-kubelet.conf overwrite: true This will need
        to be done for each relevant MachineConfigPool in the cluster. After enabling
        this and after the changes have successfully rolled out to the whole cluster,
        it will now be possible to set the protectKernelDefaults parameter. To configure,
        follow the directions in the documentation"
    - name: file_owner_kubelet_conf
      description: 'To properly set the owner of /etc/kubernetes/kubelet.conf, run
        the command: $ sudo chown root /etc/kubernetes/kubelet.conf'
    - name: file_owner_kubelet
      description: 'To properly set the owner of /var/lib/kubelet/config.json, run
        the command: $ sudo chown root /var/lib/kubelet/config.json'
    - name: file_groupowner_multus_conf
      description: 'To properly set the group owner of /var/run/multus/cni/net.d/*,
        run the command: $ sudo chgrp root /var/run/multus/cni/net.d/*'
    - name: kubelet_enable_iptables_util_chains
      description: 'The kubelet has the ability to automatically configure the firewall
        to allow the containers required ports and connections to networking resources
        and destinations parameters potentially creating a security incident. To allow
        the kubelet to modify the firewall, edit the kubelet configuration file /etc/kubernetes/kubelet.conf
        on the kubelet node(s) and set the below parameter: makeIPTablesUtilChains:
        true'
    - name: controller_service_account_private_key
      description: 'To ensure the API Server utilizes its own key pair, set the privateKeyFile
        parameter to the public key file for service accounts in the openshift-kube-controller-manager
        configmap on the master node(s): "extendedArguments": { ... "service-account-private-key-file":
        [ "/etc/kubernetes/static-pod-resources/secrets/service-account-private-key/service-account.key"
        ], ...'
    - name: file_owner_worker_ca
      description: 'To properly set the owner of /etc/kubernetes/kubelet-ca.crt, run
        the command: $ sudo chown root /etc/kubernetes/kubelet-ca.crt'
    - name: file_permissions_kube_apiserver
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/kube-apiserver-pod-*/kube-apiserver-pod.yaml,
        run the command: $ sudo chmod 0600 /etc/kubernetes/static-pod-resources/kube-apiserver-pod-*/kube-apiserver-pod.yaml'
    - name: file_owner_ovs_pid
      description: 'To properly set the owner of /var/run/openvswitch/ovs-vswitchd.pid,
        run the command: $ sudo chown openvswitch /var/run/openvswitch/ovs-vswitchd.pid'
    - name: kubelet_configure_event_creation
      description: 'Security relevant information should be captured. The eventRecordQPS
        Kubelet option can be used to limit the rate at which events are gathered.
        Setting this too low could result in relevant events not being logged, however
        the unlimited setting of 0 could result in a denial of service on the kubelet.
        Processing and storage systems should be scaled to handle the expected event
        load. To set the eventRecordQPS option for the kubelet, create a KubeletConfig
        option along these lines: apiVersion: machineconfiguration.openshift.io/v1
        kind: KubeletConfig metadata: name: kubelet-config-$pool spec: machineConfigPoolSelector:
        matchLabels: pools.operator.machineconfiguration.openshift.io/$pool_name:
        "" kubeletConfig: eventRecordQPS:'
    - name: file_owner_worker_service
      description: "' To properly set the owner of /etc/systemd/system/kubelet.service,
        run the command: $ sudo chown root /etc/systemd/system/kubelet.service '"
    - name: etcd_key_file
      description: 'To ensure the etcd service is serving TLS to clients, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: oc get -nopenshift-etcd cm etcd-pod
        -oyaml | grep "\-\-key-file=/etc/kubernetes/static-pod-certs/secrets/etcd-all-[a-z]+/etcd-serving-NODE_NAME.key".
        Note that the [a-z]+ is being used since the directory might change between
        OpenShift versions.'
    - name: file_permissions_master_admin_kubeconfigs
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/kube-apiserver-certs/secrets/node-kubeconfigs/*.kubeconfig,
        run the command: $ sudo chmod 0600 /etc/kubernetes/static-pod-resources/kube-apiserver-certs/secrets/node-kubeconfigs/*.kubeconfig'
    - name: file_groupowner_etcd_pki_cert_files
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/*/*/*/*.crt,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/*/*/*/*.crt'
    - name: api_server_insecure_bind_address
      description: 'OpenShift should not bind to non-loopback insecure addresses.
        Edit the openshift-kube-apiserver configmap and remove the insecure-bind-address
        if it exists: "apiServerArguments":{ ... "insecure-bind-address":[ "127.0.0.1"
        ], ...'
    - name: file_permissions_proxy_kubeconfig
      description: 'To ensure the Kubernetes ConfigMap is mounted into the sdn daemonset
        pods with the correct permissions, make sure that the sdn-config ConfigMap
        is mounted using restrictive permissions. Check that the config VolumeMount
        mounts the sdn-config configMap with permissions set to 420: { "configMap":
        { "defaultMode": 420, "name": "sdn-config" }, "name": "config" }'
    - name: kubelet_enable_client_cert_rotation
      description: 'To enable the kubelet to rotate client certificates, edit the
        kubelet configuration file /etc/kubernetes/kubelet.conf on the kubelet node(s)
        and set the below parameter: featureGates: ... RotateKubeletClientCertificate:
        true ...'
    - name: file_permissions_ovs_sys_id_conf
      description: 'To properly set the permissions of /etc/openvswitch/system-id.conf,
        run the command: $ sudo chmod 0644 /etc/openvswitch/system-id.conf'
    - name: file_owner_kube_apiserver
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/kube-apiserver-pod-*/kube-apiserver-pod.yaml,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/kube-apiserver-pod-*/kube-apiserver-pod.yaml'
    - name: file_owner_ovs_conf_db
      description: 'To properly set the owner of /etc/openvswitch/conf.db, run the
        command: $ sudo chown openvswitch /etc/openvswitch/conf.db'
    - name: kubelet_anonymous_auth
      description: 'By default, anonymous access to the Kubelet server is enabled.
        This configuration check ensures that anonymous requests to the Kubelet server
        are disabled. Edit the Kubelet server configuration file /etc/kubernetes/kubelet.conf
        on the kubelet node(s) and set the below parameter: authentication: ... anonymous:
        enabled: false ...'
    - name: file_owner_controller_manager_kubeconfig
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/configmaps/controller-manager-kubeconfig/kubeconfig,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/configmaps/controller-manager-kubeconfig/kubeconfig'
    - name: file_groupowner_openshift_sdn_cniserver_config
      description: 'To properly set the group owner of /var/run/openshift-sdn/cniserver/config.json,
        run the command: $ sudo chgrp root /var/run/openshift-sdn/cniserver/config.json'
    - name: rbac_wildcard_use
      description: Kubernetes Cluster and Local Roles provide access to resources
        based on sets of objects and actions that can be taken on those objects. It
        is possible to set either of these using a wildcard * which matches all items.
        This violates the principle of least privilege and leaves a cluster in a more
        vulnerable state to privilege abuse.
    - name: file_groupowner_proxy_kubeconfig
      description: "To ensure the Kubernetes ConfigMap is mounted into the sdn daemonset
        pods with the correct ownership, make sure that the sdn-config ConfigMap is
        mounted using a ConfigMap at the /config mount point and that the sdn container
        points to that configuration using the --proxy-config command line option.
        Run: oc get -nopenshift-sdn ds sdn -ojson | jq -r '.spec.template.spec.containers[]
        | select(.name == \"sdn\")' and ensure the --proxy-config parameter points
        to /config/kube-proxy-config.yaml and that the config mount point is mounted
        from the sdn-config ConfigMap."
    - name: general_apply_scc
      description: Apply Security Context to your Pods and Containers
    - name: etcd_cert_file
      description: 'To ensure the etcd service is serving TLS to clients, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: --cert-file=/etc/kubernetes/static-pod-certs/secrets/etcd-all-[a-z]+/etcd-serving-NODE_NAME.crt.
        Note that the [a-z]+ is being used since the directory might change between
        OpenShift versions.'
    - name: api_server_auth_mode_rbac
      description: To ensure OpenShift restricts different identities to a defined
        set of operations they are allowed to perform, check that the API server's
        authorization-mode configuration option list contains RBAC.
    - name: file_permissions_etcd_pki_cert_files
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/etcd-*/secrets/*/*.crt,
        run the command: $ sudo chmod 0600 /etc/kubernetes/static-pod-resources/etcd-*/secrets/*/*.crt'
    - name: general_configure_imagepolicywebhook
      description: 'OpenShift administrators can control which images can be imported,
        tagged, and run in a cluster. There are two facilities for this purpose: (1)
        Allowed Registries, allowing administrators to restrict image origins to known
        external registries; and (2) ImagePolicy Admission plug-in which lets administrators
        specify specific images which are allowed to run on the OpenShift cluster.
        Configure an Image policy per the Image Policy chapter in the OpenShift documentation:
        https://docs.openshift.com/container-platform/4.4/openshift_images/image-configuration.html'
    - name: file_permissions_etcd_data_files
      description: 'To properly set the permissions of /var/lib/etcd/member/wal/*,
        run the command: $ sudo chmod 0600 /var/lib/etcd/member/wal/*'
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
    - name: file_owner_etcd_data_files
      description: 'To properly set the owner of /var/lib/etcd/member/wal/*, run the
        command: $ sudo chown root /var/lib/etcd/member/wal/*'
    - name: file_permissions_etcd_member
      description: 'To properly set the permissions of /etc/kubernetes/manifests/etcd-pod.yaml,
        run the command: $ sudo chmod 0600 /etc/kubernetes/manifests/etcd-pod.yaml'
    - name: file_groupowner_scheduler_kubeconfig
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/configmaps/scheduler-kubeconfig/kubeconfig,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/configmaps/scheduler-kubeconfig/kubeconfig'
    - name: openshift_api_server_audit_log_path
      description: 'To enable auditing on the OpenShift API Server, the audit log
        path must be set. Edit the openshift-apiserver configmap and set the audit-log-path
        to a suitable path and file where audit logs should be written. For example:
        "apiServerArguments":{ ... "audit-log-path":"/var/log/openshift-apiserver/audit.log",
        ...'
    - name: api_server_profiling_protected_by_rbac
      description: Ensure that the cluster-debugger cluster role includes the /metrics
        resource URL. This demonstrates that profiling is protected by RBAC, with
        a specific cluster role to allow access.
    - name: api_server_admission_control_plugin_alwaysadmit
      description: To ensure OpenShift only responses to requests explicitly allowed
        by the admission control plugin. Check that the config ConfigMap object does
        not contain the AlwaysAdmit plugin.
    - name: scc_limit_container_allowed_capabilities
      description: 'Containers should not enable more capabilites than needed as this
        opens the door for malicious use. To enable only the required capabilities,
        the appropriate Security Context Constraints (SCCs) should set capabilities
        as a list in allowedCapabilities. In case an SCC outside the default allow
        list in the variable var-sccs-with-allowed-capabilities-regex is being flagged,
        create a TailoredProfile and add the additional SCC to the regular expression
        in the variable var-sccs-with-allowed-capabilities-regex. An example allowing
        an SCC named additional follows: apiVersion: compliance.openshift.io/v1alpha1
        kind: TailoredProfile metadata: name: cis-additional-scc spec: description:
        Allows an additional scc setValues: - name: ocp4-var-sccs-with-allowed-capabilities-regex
        rationale: Allow our own custom SCC value: ^privileged$|^hostnetwork-v2$|^restricted-v2$|^nonroot-v2$|^additional$
        extends: ocp4-cis title: Modified CIS allowing one more SCC Finally, reference
        this TailoredProfile in a ScanSettingBinding For more information on Tailoring
        the Compliance Operator, please consult the OpenShift documentation: https://docs.openshift.com/container-platform/latest/security/compliance_operator/co-scans/compliance-operator-tailor.html'
    - name: file_owner_multus_conf
      description: 'To properly set the owner of /var/run/multus/cni/net.d/*, run
        the command: $ sudo chown root /var/run/multus/cni/net.d/*'
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
    - name: api_server_basic_auth
      description: 'Basic Authentication should not be used for any reason. If needed,
        edit API Edit the openshift-kube-apiserver configmap and remove the basic-auth-file
        parameter: "apiServerArguments":{ ... "basic-auth-file":[ "/path/to/any/file"
        ], ... Alternate authentication mechanisms such as tokens and certificates
        will need to be used. Username and password for basic authentication will
        be disabled.'
    - name: api_server_etcd_cert
      description: 'To ensure etcd is configured to make use of TLS encryption for
        client communications, follow the OpenShift documentation and setup the TLS
        connection between the API Server and etcd. Then, verify that apiServerArguments
        has the etcd-certfile configured in the openshift-kube-apiserver configmap
        to something similar to: ... "etcd-certfile": [ "/etc/kubernetes/static-pod-resources/secrets/etcd-client/tls.crt"
        ], ...'
    - name: file_permissions_scheduler
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/kube-scheduler-pod.yaml,
        run the command: $ sudo chmod 0644 /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/kube-scheduler-pod.yaml'
    - name: kubelet_eviction_thresholds_set_hard_imagefs_available
      description: 'Two types of garbage collection are performed on an OpenShift
        Container Platform node: Container garbage collection: Removes terminated
        containers. Image garbage collection: Removes images not referenced by any
        running pods. Container garbage collection can be performed using eviction
        thresholds. Image garbage collection relies on disk usage as reported by cAdvisor
        on the node to decide which images to remove from the node. The OpenShift
        administrator can configure how OpenShift Container Platform performs garbage
        collection by creating a kubeletConfig object for each Machine Config Pool
        using any combination of the following: soft eviction for containers hard
        eviction for containers eviction for images To configure, follow the directions
        in the documentation This rule pertains to the imagefs.available setting of
        the evictionHard section. Remediation will set field imagefs.available to
        {{ .var_kubelet_evictionhard_imagefs_available }} based on the variable var_kubelet_evictionhard_imagefs_available.'
    - name: etcd_client_cert_auth
      description: 'To ensure the etcd service is serving TLS to clients, make sure
        the etcd-pod* ConfigMaps in the openshift-etcd namespace contain the following
        argument for the etcd binary in the etcd pod: oc get -nopenshift-etcd cm etcd-pod
        -oyaml | grep "\-\-client-cert-auth=" the parameter should be set to true.'
    - name: api_server_anonymous_auth
      description: "By default, anonymous access to the OpenShift API is enabled,
        but at the same time, all requests must be authorized. If no authentication
        mechanism is used, the request is assigned the system:anonymous virtual user
        and the system:unauthenticated virtual group. This allows the authorization
        layer to determine which requests, if any, is an anonymous user authorized
        to make. To verify the authorization rules for anonymous requests run the
        following: $ oc describe clusterrolebindings and inspect the bindings of the
        system:anonymous virtual user and the system:unauthenticated virtual group.
        To test that an anonymous request is authorized to access the readyz endpoint,
        run: $ oc get --as=\"system:anonymous\" --raw='/readyz?verbose' In contrast,
        a request to list all projects should not be authorized: $ oc get --as=\"\
        system:anonymous\" projects"
    - name: scc_limit_process_id_namespace
      description: Containers should not be allowed access to the host's process ID
        namespace. To prevent containers from getting access to a host's process ID
        namespace, the appropriate Security Context Constraints (SCCs) should set
        allowHostPID to false.
    - name: scc_drop_container_capabilities
      description: Containers should not enable more capabilities than needed as this
        opens the door for malicious use. To disable the capabilities, the appropriate
        Security Context Constraints (SCCs) should set all capabilities as * or a
        list of capabilities in requiredDropCapabilities.
    - name: controller_insecure_port_disabled
      description: 'To ensure the Controller Manager service is bound to secure loopback
        address and a secure port, set the RotateKubeletServerCertificate option to
        true in the openshift-kube-controller-manager configmap on the master node(s):
        "extendedArguments": { ... "port": ["0"], ... It is also acceptable for a
        system to deprecate the insecure port: "extendedArguments": { ... ...'
    - name: api_server_no_adm_ctrl_plugins_disabled
      description: "To make sure none of them is explicitly disabled except PodSecurity,
        run the following command: $ oc -n openshift-kube-apiserver get configmap
        config -o json | jq -r '[.data.\"config.yaml\" | fromjson | .apiServerArguments
        | select(has(\"disable-admission-plugins\")) | if .\"disable-admission-plugins\"\
        \ != [\"PodSecurity\"] then .\"disable-admission-plugins\" else empty end]'
        and make sure the output is empty."
    - name: file_groupowner_kube_controller_manager
      description: 'To properly set the group owner of /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/kube-controller-manager-pod.yaml,
        run the command: $ sudo chgrp root /etc/kubernetes/static-pod-resources/kube-controller-manager-pod-*/kube-controller-manager-pod.yaml'
    - name: file_permissions_ip_allocations
      description: 'To properly set the permissions of /var/lib/cni/networks/openshift-sdn/*,
        run the command: $ sudo chmod 0644 /var/lib/cni/networks/openshift-sdn/*'
    - name: file_owner_etcd_member
      description: 'To properly set the owner of /etc/kubernetes/manifests/etcd-pod.yaml,
        run the command: $ sudo chown root /etc/kubernetes/manifests/etcd-pod.yaml'
    - name: file_permissions_scheduler_kubeconfig
      description: 'To properly set the permissions of /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/configmaps/scheduler-kubeconfig/kubeconfig,
        run the command: $ sudo chmod 0600 /etc/kubernetes/static-pod-resources/kube-scheduler-pod-*/configmaps/scheduler-kubeconfig/kubeconfig'
    - name: scansettingbinding_exists
      description: The Compliance Operator scans the hosts and the platform (OCP)
        configurations for software flaws and improper configurations according to
        different compliance benchmarks. It uses OpenSCAP as a backend, which is a
        known and certified tool to do such scans.
    - name: general_default_seccomp_profile
      description: Enable default seccomp profiles in your pod definitions.
    - name: file_owner_ip_allocations
      description: 'To properly set the owner of /var/lib/cni/networks/openshift-sdn/.*,
        run the command: $ sudo chown root /var/lib/cni/networks/openshift-sdn/.*'
    - name: file_permissions_ovn_cni_server_sock
      description: 'To properly set the permissions of /run/ovn-kubernetes/cni/ovn-cni-server.sock,
        run the command: $ sudo chmod 0600 /run/ovn-kubernetes/cni/ovn-cni-server.sock'
    - name: file_groupowner_ovn_cni_server_sock
      description: 'To properly set the group owner of /run/ovn-kubernetes/cni/ovn-cni-server.sock,
        run the command: $ sudo chgrp root /run/ovn-kubernetes/cni/ovn-cni-server.sock'
    - name: file_owner_ovn_cni_server_sock
      description: 'To properly set the owner of /run/ovn-kubernetes/cni/ovn-cni-server.sock,
        run the command: $ sudo chown root /run/ovn-kubernetes/cni/ovn-cni-server.sock'
    - name: file_groupowner_ovn_db_files
      description: 'To properly set the group owner of /var/lib/ovn/etc/*.db, run
        the command: $ sudo chgrp root /var/lib/ovn/etc/*.db'
    - name: file_owner_ovn_db_files
      description: 'To properly set the owner of /var/lib/ovn/etc/*.db, run the command:
        $ sudo chown root /var/lib/ovn/etc/*.db'
    - name: file_permissions_ovn_db_files
      description: 'To properly set the permissions of /var/lib/ovn/etc/*.db, run
        the command: $ sudo chmod 0640 /var/lib/ovn/etc/*.db'
    - name: api_server_oauth_https_serving_cert
      description: By default, the OpenShift OAuth API Server uses TLS. HTTPS should
        be used for connections between openshift-oauth-apiserver and kube-apiserver.
        By default, the OpenShift OAuth API Server uses Intermediate profile which
        requires a minimum TLS version of 1.2.
    - name: file_permissions_ovs_vswitchd_pid
      description: 'To properly set the permissions of /run/openvswitch/ovs-vswitchd.pid,
        run the command: $ sudo chmod 0644 /run/openvswitch/ovs-vswitchd.pid'
    - name: secrets_consider_external_storage
      description: Consider the use of an external secrets storage and management
        system, instead of using Kubernetes Secrets directly, if you have more complex
        secret management needs. Ensure the solution requires authentication to access
        secrets, has auditing of access to and use of secrets, and encrypts secrets.
        Some solutions also make it easier to rotate secrets.
    - name: kubelet_enable_cert_rotation
      description: 'To enable the kubelet to rotate client certificates, edit the
        kubelet configuration file /etc/kubernetes/kubelet.conf on the kubelet node(s)
        and set the below parameter: ... rotateCertificates: true ...'
    - name: kubelet_disable_readonly_port
      description: 'To disable the read-only port, edit the kubelet configuration
        Edit the openshift-kube-apiserver configmap and set the kubelet-read-only-port
        parameter to 0: "apiServerArguments":{ ... "kubelet-read-only-port":[ "0"
        ], ...'
    - name: configure_network_policies
      description: There are a variety of CNI plugins available for Kubernetes. If
        the CNI in use does not support Network Policies it may not be possible to
        effectively restrict traffic in the cluster. OpenShift supports Kubernetes
        NetworkPolicy using a Kubernetes Container Network Interface (CNI) plug-in.
    - name: api_server_admission_control_plugin_scc
      description: To ensure pod permissions are managed, make sure that the SecurityContextConstraint
        admission control plugin is used.
    - name: file_owner_etcd_pki_cert_files
      description: 'To properly set the owner of /etc/kubernetes/static-pod-resources/*/*/*/*.crt,
        run the command: $ sudo chown root /etc/kubernetes/static-pod-resources/*/*/*/*.crt'
    - name: file_groupowner_etcd_data_dir
      description: 'To properly set the group owner of /var/lib/etcd/member/, run
        the command: $ sudo chgrp root /var/lib/etcd/member/'
    - name: etcd_auto_tls
      description: 'To ensure the etcd service is not using self-signed certificates,
        run the following command: $ oc get cm/etcd-pod -n openshift-etcd -o yaml
        The etcd pod configuration contained in the configmap should not contain the
        --auto-tls=true flag.'
    - name: api_server_admission_control_plugin_alwayspullimages
      description: The AlwaysPullImages admission control plugin should be disabled,
        since it can introduce new failure modes for control plane components if an
        image registry is unreachable.
    - name: controller_use_service_account
      description: 'To ensure individual service account credentials are used, set
        the use-service-account-credentials option to true in the openshift-kube-controller-manager
        configmap on the master node(s): "extendedArguments": { ... "use-service-account-credentials":
        [ "true" ], ...'
    - name: file_groupowner_ovs_sys_id_conf
      description: Check if the group owner of /etc/openvswitch/system-id.conf is
        hugetlbfs on architectures other than s390x or openvswitch on x390x.
    - name: file_groupowner_cni_conf
      description: 'To properly set the group owner of /etc/cni/net.d/*, run the command:
        $ sudo chgrp root /etc/cni/net.d/*'
    - name: rbac_debug_role_protects_pprof
      description: Ensure that the cluster-debugger cluster role includes the /debug/pprof
        resource URL. This demonstrates that profiling is protected by RBAC, with
        a specific cluster role to allow access.
    - name: rbac_limit_cluster_admin
      description: The RBAC role cluster-admin provides wide-ranging powers over the
        environment and should be used only where and when needed.
    - name: file_groupowner_ovs_pid
      description: Ensure that the file /var/run/openvswitch/ovs-vswitchd.pid, is
        owned by the group openvswitch or hugetlbfs, depending on your settings and
        Open vSwitch version.
    - name: api_server_admission_control_plugin_securitycontextdeny
      description: "Instead of using a customized SecurityContext for pods, a Pod
        Security Policy (PSP) or a SecurityContextConstraint should be used. These
        are cluster-level resources that control the actions that a pod can perform
        and what resource the pod may access. The SecurityContextDeny disallows folks
        from setting a pod's securityContext fields. Ensure that the list of admission
        controllers does not include SecurityContextDeny: $ oc -n openshift-kube-apiserver
        get configmap config -o json | jq -r '.data.\"config.yaml\"' | jq '.apiServerArguments.\"\
        enable-admission-plugins\"'"
    - name: file_groupowner_ovs_conf_db_lock
      description: Check if the group owner of /etc/openvswitch/.conf.db.~lock~ is
        hugetlbfs on architectures other than s390x or openvswitch on s390x.
    - name: file_owner_ovsdb_server_pid
      description: 'To properly set the owner of /run/openvswitch/ovsdb-server.pid,
        run the command: $ sudo chown openvswitch /run/openvswitch/ovsdb-server.pid'
    - name: kubelet_configure_tls_cipher_suites
      description: 'Ensure that the Kubelet is configured to only use strong cryptographic
        ciphers. To set the cipher suites for the kubelet, create new or modify existing
        KubeletConfig object along these lines, one for every MachineConfigPool: apiVersion:
        machineconfiguration.openshift.io/v1 kind: KubeletConfig metadata: name: kubelet-config-$pool
        spec: machineConfigPoolSelector: matchLabels: pools.operator.machineconfiguration.openshift.io/$pool_name:
        "" kubeletConfig: tlsCipherSuites: - TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
        - TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384 - TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
        - TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256 - TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256
        - TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256 In order to configure this rule
        to check for an alternative cipher, both var_kubelet_tls_cipher_suites_regex
        and var_kubelet_tls_cipher_suites have to be set'
    - name: scc_limit_network_namespace
      description: Containers should not be allowed access to the host's network namespace.
        To prevent containers from getting access to a host's network namespace, the
        appropriate Security Context Constraints (SCCs) should set allowHostNetwork
        to false.
    - name: file_groupowner_ovs_conf_db
      description: Check if the group owner of /etc/openvswitch/conf.db is hugetlbfs
        on architectures other than s390x or openvswitch on s390x.
x-trestle-rules-params:
  ocp4:
    - name: var_api_min_request_timeout
      description: Enter API Server Request Timeout
      options: "{300: '300', 'default': '3600'}"
      rule-id: api_server_request_timeout
    - name: var_apiserver_bind_address
      description: Bind Address of secure API endpoint
      options: "{'default': '0.0.0.0:6443'}"
      rule-id: api_server_bind_address
    - name: var_kubelet_tls_cipher_suites_regex
      description: Cryptographic Ciphers Available for Kubelet
      options: "{'default': '^(TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384|TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256|TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256|TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256|TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256)$'}"
      rule-id: kubelet_configure_tls_cipher_suites
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
    - name: var_api_min_request_timeout
      values:
        - '3600'
    - name: var_apiserver_bind_address
      values:
        - 0.0.0.0:6443
    - name: var_kubelet_tls_cipher_suites_regex
      values:
        - ^(TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384|TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256|TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256|TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256|TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256)$
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
  cm-06_odp.01:
    alt-identifier: cm-6_prm_1
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  cm-06_odp.02:
    alt-identifier: cm-6_prm_2
    profile-values:
      - <REPLACE_ME>
    profile-param-value-origin: <REPLACE_ME>
  cm-06_odp.03:
    alt-identifier: cm-6_prm_3
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
  sort-id: cm-06
---

# cm-6 - \[Configuration Management\] Configuration Settings

## Control Statement

- \[a.\] Establish and document configuration settings for components employed within the system that reflect the most restrictive mode consistent with operational requirements using [common secure configurations];

- \[b.\] Implement the configuration settings;

- \[c.\] Identify, document, and approve any deviations from established configuration settings for [system components] based on [operational requirements] ; and

- \[d.\] Monitor and control changes to the configuration settings in accordance with organizational policies and procedures.

- \[cm-6_fr\]

  - \[(a) Requirement 1:\] The service provider shall use the DoD STIGs or Center for Internet Security guidelines to establish configuration settings;
  - \[(a) Requirement 2:\] The service provider shall ensure that checklists for configuration settings are Security Content Automation Protocol (SCAP) validated or SCAP compatible (if validated checklists are not available).

## Control Assessment Objective

- \[CM-06a.\] configuration settings that reflect the most restrictive mode consistent with operational requirements are established and documented for components employed within the system using [common secure configurations];

- \[CM-06b.\] the configuration settings documented in CM-06a are implemented;

- \[CM-06c.\]

  - \[CM-06c.[01]\] any deviations from established configuration settings for [system components] are identified and documented based on [operational requirements];
  - \[CM-06c.[02]\] any deviations from established configuration settings for [system components] are approved;

- \[CM-06d.\]

  - \[CM-06d.[01]\] changes to the configuration settings are monitored in accordance with organizational policies and procedures;
  - \[CM-06d.[02]\] changes to the configuration settings are controlled in accordance with organizational policies and procedures.

## Control guidance

Compliance checks are used to evaluate configuration settings and provide general insight into the overall effectiveness of configuration management activities. CSPs and 3PAOs typically combine compliance check findings into a single CM-6 finding, which is acceptable. However, for initial assessments, annual assessments, and significant change requests, FedRAMP requires a clear understanding, on a per-control basis, where risks exist. Therefore, 3PAOs must also analyze compliance check findings as part of the controls assessment. Where a direct mapping exists, the 3PAO must document additional findings per control in the corresponding SAR Risk Exposure Table (RET), which are then documented in the CSP's Plan of Action and Milestones (POA&M). This will likely result in the details of individual control findings overlapping with those in the combined CM-6 finding, which is acceptable.

During monthly continuous monitoring, new findings from CSP compliance checks may be combined into a single CM-6 POA&M item. CSPs are not required to map the findings to specific controls because controls are only assessed during initial assessments, annual assessments, and significant change requests.

Configuration settings are the parameters that can be changed in the hardware, software, or firmware components of the system that affect the security and privacy posture or functionality of the system. Information technology products for which configuration settings can be defined include mainframe computers, servers, workstations, operating systems, mobile devices, input/output devices, protocols, and applications. Parameters that impact the security posture of systems include registry settings; account, file, or directory permission settings; and settings for functions, protocols, ports, services, and remote connections. Privacy parameters are parameters impacting the privacy posture of systems, including the parameters required to satisfy other privacy controls. Privacy parameters include settings for access controls, data processing preferences, and processing and retention permissions. Organizations establish organization-wide configuration settings and subsequently derive specific configuration settings for systems. The established settings become part of the configuration baseline for the system.

Common secure configurations (also known as security configuration checklists, lockdown and hardening guides, and security reference guides) provide recognized, standardized, and established benchmarks that stipulate secure configuration settings for information technology products and platforms as well as instructions for configuring those products or platforms to meet operational requirements. Common secure configurations can be developed by a variety of organizations, including information technology product developers, manufacturers, vendors, federal agencies, consortia, academia, industry, and other organizations in the public and private sectors.

Implementation of a common secure configuration may be mandated at the organization level, mission and business process level, system level, or at a higher level, including by a regulatory agency. Common secure configurations include the United States Government Configuration Baseline [USGCB](#98498928-3ca3-44b3-8b1e-f48685373087) and security technical implementation guides (STIGs), which affect the implementation of [CM-6](#cm-6) and other controls such as [AC-19](#ac-19) and [CM-7](#cm-7) . The Security Content Automation Protocol (SCAP) and the defined standards within the protocol provide an effective method to uniquely identify, track, and control configuration settings.

______________________________________________________________________

## What is the solution and how is it implemented?

<!-- For implementation status enter one of: implemented, partial, planned, alternative, not-applicable -->

<!-- Note that the list of rules under ### Rules: is read-only and changes will not be captured after assembly to JSON -->

### This System

<!-- Add implementation prose for the main This System component for control: cm-6 -->

#### Implementation Status: planned

### ocp4

REPLACE_ME

#### Rules:

  - file_perms_openshift_sdn_cniserver_config
  - file_owner_openshift_sdn_cniserver_config
  - api_server_admission_control_plugin_namespacelifecycle
  - api_server_request_timeout
  - file_permissions_openshift_pki_key_files
  - file_owner_cni_conf
  - ocp_api_server_audit_log_maxsize
  - file_owner_master_admin_kubeconfigs
  - file_permissions_ovsdb_server_pid
  - file_groupowner_kube_scheduler
  - file_groupowner_etcd_member
  - file_permissions_openshift_pki_cert_files
  - kubelet_enable_server_cert_rotation
  - file_permissions_ovs_conf_db_lock
  - rbac_limit_secrets_access
  - file_permissions_worker_service
  - api_server_bind_address
  - api_server_audit_log_path
  - file_permissions_kubelet_conf
  - file_permissions_kubelet
  - api_server_https_for_kubelet_conn
  - file_owner_ovs_vswitchd_pid
  - api_server_audit_log_maxbackup
  - file_owner_ovs_conf_db_lock
  - file_owner_scheduler_kubeconfig
  - file_permissions_multus_conf
  - ocp_api_server_audit_log_maxbackup
  - etcd_peer_auto_tls
  - file_groupowner_worker_kubeconfig
  - file_permissions_kube_controller_manager
  - kubelet_eviction_thresholds_set_hard_nodefs_available
  - file_groupowner_kube_apiserver
  - file_owner_kube_scheduler
  - accounts_restrict_service_account_tokens
  - file_groupowner_ovs_vswitchd_pid
  - scc_limit_ipc_namespace
  - api_server_kubelet_certificate_authority
  - scc_limit_privileged_containers
  - file_groupowner_openshift_pki_key_files
  - controller_secure_port
  - api_server_service_account_public_key
  - secrets_no_environment_variables
  - api_server_admission_control_plugin_noderestriction
  - kubelet_configure_client_ca
  - file_owner_ovs_sys_id_conf
  - file_permissions_cni_conf
  - file_groupowner_worker_service
  - file_owner_etcd_data_dir
  - file_groupowner_controller_manager_kubeconfig
  - api_server_api_priority_flowschema_catch_all
  - api_server_audit_log_maxsize
  - file_permissions_etcd_data_dir
  - api_server_etcd_key
  - general_default_namespace_use
  - scc_limit_privilege_escalation
  - rbac_pod_creation_access
  - file_groupowner_worker_ca
  - api_server_auth_mode_no_aa
  - file_permissions_ovs_pid
  - file_groupowner_ovsdb_server_pid
  - file_groupowner_ip_allocations
  - file_permissions_ovs_conf_db
  - kubelet_eviction_thresholds_set_hard_memory_available
  - api_server_token_auth
  - directory_permissions_var_log_oauth_audit
  - file_owner_worker_kubeconfig
  - file_permissions_controller_manager_kubeconfig
  - file_ownership_var_log_kube_audit
  - controller_service_account_ca
  - file_permissions_worker_ca
  - kubelet_enable_streaming_connections
  - kubelet_authorization_mode
  - configure_network_policies_namespaces
  - etcd_unique_ca
  - directory_permissions_var_log_ocp_audit
  - file_owner_openshift_pki_cert_files
  - kubelet_eviction_thresholds_set_hard_nodefs_inodesfree
  - scc_limit_net_raw_capability
  - file_permissions_worker_kubeconfig
  - directory_access_var_log_ocp_audit
  - scc_limit_root_containers
  - file_owner_openshift_pki_key_files
  - directory_access_var_log_kube_audit
  - etcd_peer_client_cert_auth
  - file_groupowner_master_admin_kubeconfigs
  - file_integrity_exists
  - file_owner_proxy_kubeconfig
  - file_groupowner_etcd_data_files
  - api_server_auth_mode_node
  - controller_rotate_kubelet_server_certs
  - api_server_openshift_https_serving_cert
  - api_server_service_account_lookup
  - file_groupowner_openshift_pki_cert_files
  - file_permissions_var_log_kube_audit
  - general_namespaces_in_use
  - file_groupowner_kubelet_conf
  - file_permissions_var_log_ocp_audit
  - accounts_unique_service_account
  - api_server_admission_control_plugin_service_account
  - file_owner_kube_controller_manager
  - kubelet_enable_protect_kernel_sysctl
  - kubelet_enable_protect_kernel_defaults
  - file_owner_kubelet_conf
  - file_owner_kubelet
  - file_groupowner_multus_conf
  - kubelet_enable_iptables_util_chains
  - controller_service_account_private_key
  - file_owner_worker_ca
  - file_permissions_kube_apiserver
  - file_owner_ovs_pid
  - kubelet_configure_event_creation
  - file_owner_worker_service
  - directory_access_var_log_oauth_audit
  - etcd_key_file
  - file_permissions_master_admin_kubeconfigs
  - file_groupowner_etcd_pki_cert_files
  - api_server_insecure_bind_address
  - file_permissions_proxy_kubeconfig
  - kubelet_enable_client_cert_rotation
  - file_permissions_ovs_sys_id_conf
  - file_owner_kube_apiserver
  - file_owner_ovs_conf_db
  - kubelet_anonymous_auth
  - file_owner_controller_manager_kubeconfig
  - file_groupowner_openshift_sdn_cniserver_config
  - rbac_wildcard_use
  - file_groupowner_proxy_kubeconfig
  - general_apply_scc
  - etcd_cert_file
  - api_server_auth_mode_rbac
  - file_ownership_var_log_oauth_audit
  - file_permissions_etcd_pki_cert_files
  - general_configure_imagepolicywebhook
  - file_permissions_etcd_data_files
  - api_server_kubelet_client_cert
  - api_server_kubelet_client_cert_pre_4_9
  - file_owner_etcd_data_files
  - file_permissions_etcd_member
  - file_groupowner_scheduler_kubeconfig
  - file_ownership_var_log_ocp_audit
  - openshift_api_server_audit_log_path
  - api_server_profiling_protected_by_rbac
  - api_server_admission_control_plugin_alwaysadmit
  - scc_limit_container_allowed_capabilities
  - file_owner_multus_conf
  - api_server_kubelet_client_key
  - api_server_kubelet_client_key_pre_4_9
  - api_server_basic_auth
  - api_server_etcd_cert
  - file_permissions_scheduler
  - kubelet_eviction_thresholds_set_hard_imagefs_available
  - etcd_client_cert_auth
  - api_server_anonymous_auth
  - file_permissions_var_log_oauth_audit
  - scc_limit_process_id_namespace
  - scc_drop_container_capabilities
  - controller_insecure_port_disabled
  - api_server_no_adm_ctrl_plugins_disabled
  - file_groupowner_kube_controller_manager
  - file_permissions_ip_allocations
  - file_owner_etcd_member
  - file_permissions_scheduler_kubeconfig
  - scansettingbinding_exists
  - general_default_seccomp_profile
  - file_owner_ip_allocations
  - file_permissions_ovn_cni_server_sock
  - file_groupowner_ovn_cni_server_sock
  - file_owner_ovn_cni_server_sock
  - file_groupowner_ovn_db_files
  - file_owner_ovn_db_files
  - file_permissions_ovn_db_files
  - api_server_oauth_https_serving_cert
  - file_permissions_ovs_vswitchd_pid
  - secrets_consider_external_storage
  - kubelet_enable_cert_rotation
  - kubelet_disable_readonly_port
  - configure_network_policies
  - api_server_admission_control_plugin_scc
  - file_owner_etcd_pki_cert_files
  - file_groupowner_etcd_data_dir
  - etcd_auto_tls
  - api_server_admission_control_plugin_alwayspullimages
  - controller_use_service_account
  - file_groupowner_ovs_sys_id_conf
  - file_groupowner_cni_conf
  - rbac_debug_role_protects_pprof
  - rbac_limit_cluster_admin
  - file_groupowner_ovs_pid
  - api_server_admission_control_plugin_securitycontextdeny
  - directory_permissions_var_log_kube_audit
  - file_groupowner_ovs_conf_db_lock
  - file_owner_ovsdb_server_pid
  - kubelet_configure_tls_cipher_suites
  - scc_limit_network_namespace
  - file_groupowner_ovs_conf_db

#### Implementation Status: implemented

______________________________________________________________________
