---
---

## kube-apiserver



### Synopsis


The Kubernetes API server validates and configures data
for the api objects which include pods, services, replicationcontrollers, and
others. The API Server services REST operations and provides the frontend to the
cluster's shared state through which all other components interact.

```
kube-apiserver
```

### Options

```
      --admission-control string                                Ordered list of plug-ins to do admission control of resources into cluster. Comma-delimited list of: AlwaysAdmit, AlwaysDeny, AlwaysPullImages, DefaultStorageClass, DenyEscalatingExec, DenyExecOnPrivileged, ImagePolicyWebhook, InitialResources, LimitPodHardAntiAffinityTopology, LimitRanger, NamespaceAutoProvision, NamespaceExists, NamespaceLifecycle, PersistentVolumeLabel, PodSecurityPolicy, ResourceQuota, SecurityContextDeny, ServiceAccount. (default "AlwaysAdmit")
      --admission-control-config-file string                    File with admission control configuration.
      --advertise-address value                                 The IP address on which to advertise the apiserver to members of the cluster. This address must be reachable by the rest of the cluster. If blank, the --bind-address will be used. If --bind-address is unspecified, the host's default interface will be used.
      --allow-privileged                                        If true, allow privileged containers.
      --apiserver-count int                                     The number of apiservers running in the cluster. (default 1)
      --audit-log-maxage int                                    The maximum number of days to retain old audit log files based on the timestamp encoded in their filename.
      --audit-log-maxbackup int                                 The maximum number of old audit log files to retain.
      --audit-log-maxsize int                                   The maximum size in megabytes of the audit log file before it gets rotated. Defaults to 100MB.
      --audit-log-path string                                   If set, all requests coming to the apiserver will be logged to this file.
      --authentication-token-webhook-cache-ttl duration         The duration to cache responses from the webhook token authenticator. Default is 2m. (default 2m0s)
      --authentication-token-webhook-config-file string         File with webhook configuration for token authentication in kubeconfig format. The API server will query the remote service to determine authentication for bearer tokens.
      --authorization-mode string                               Ordered list of plug-ins to do authorization on secure port. Comma-delimited list of: AlwaysAllow,AlwaysDeny,ABAC,Webhook,RBAC. (default "AlwaysAllow")
      --authorization-policy-file string                        File with authorization policy in csv format, used with --authorization-mode=ABAC, on the secure port.
      --authorization-rbac-super-user string                    If specified, a username which avoids RBAC authorization checks and role binding privilege escalation checks, to be used with --authorization-mode=RBAC.
      --authorization-webhook-cache-authorized-ttl duration     The duration to cache 'authorized' responses from the webhook authorizer. Default is 5m. (default 5m0s)
      --authorization-webhook-cache-unauthorized-ttl duration   The duration to cache 'unauthorized' responses from the webhook authorizer. Default is 30s. (default 30s)
      --authorization-webhook-config-file string                File with webhook configuration in kubeconfig format, used with --authorization-mode=Webhook. The API server will query the remote service to determine access on the API server's secure port.
      --basic-auth-file string                                  If set, the file that will be used to admit requests to the secure port of the API server via http basic authentication.
      --bind-address value                                      The IP address on which to listen for the --secure-port port. The associated interface(s) must be reachable by the rest of the cluster, and by CLI/web clients. If blank, all interfaces will be used (0.0.0.0). (default 0.0.0.0)
      --cert-dir string                                         The directory where the TLS certs are located (by default /var/run/kubernetes). If --tls-cert-file and --tls-private-key-file are provided, this flag will be ignored. (default "/var/run/kubernetes")
      --client-ca-file string                                   If set, any request presenting a client certificate signed by one of the authorities in the client-ca-file is authenticated with an identity corresponding to the CommonName of the client certificate.
      --cloud-config string                                     The path to the cloud provider configuration file. Empty string for no configuration file.
      --cloud-provider string                                   The provider for cloud services. Empty string for no provider.
      --cors-allowed-origins value                              List of allowed origins for CORS, comma separated.  An allowed origin can be a regular expression to support subdomain matching. If this list is empty CORS will not be enabled. (default [])
      --delete-collection-workers int                           Number of workers spawned for DeleteCollection call. These are used to speed up namespace cleanup. (default 1)
      --deserialization-cache-size int                          Number of deserialized json objects to cache in memory. (default 50000)
      --enable-garbage-collector                                Enables the generic garbage collector. MUST be synced with the corresponding flag of the kube-controller-manager. (default true)
      --enable-swagger-ui                                       Enables swagger ui on the apiserver at /swagger-ui
      --etcd-cafile string                                      SSL Certificate Authority file used to secure etcd communication.
      --etcd-certfile string                                    SSL certification file used to secure etcd communication.
      --etcd-keyfile string                                     SSL key file used to secure etcd communication.
      --etcd-prefix string                                      The prefix for all resource paths in etcd. (default "/registry")
      --etcd-quorum-read                                        If true, enable quorum read.
      --etcd-servers value                                      List of etcd servers to connect with (http://ip:port), comma separated. (default [])
      --etcd-servers-overrides value                            Per-resource etcd servers overrides, comma separated. The individual override format: group/resource#servers, where servers are http://ip:port, semicolon separated. (default [])
      --event-ttl duration                                      Amount of time to retain events. Default is 1h. (default 1h0m0s)
      --experimental-keystone-url string                        If passed, activates the keystone authentication plugin.
      --external-hostname string                                The hostname to use when generating externalized URLs for this master (e.g. Swagger API Docs).
      --feature-gates value                                     A set of key=value pairs that describe feature gates for alpha/experimental features. Options are:
AllAlpha=true|false (ALPHA - default=false)
AllowExtTrafficLocalEndpoints=true|false (ALPHA - default=false)
AppArmor=true|false (BETA - default=true)
DynamicKubeletConfig=true|false (ALPHA - default=false)
DynamicVolumeProvisioning=true|false (ALPHA - default=true)
      --google-json-key string                                  The Google Cloud Platform Service Account JSON Key to use for authentication.
      --insecure-bind-address value                             The IP address on which to serve the --insecure-port (set to 0.0.0.0 for all interfaces). Defaults to localhost. (default 127.0.0.1)
      --insecure-port int                                       The port on which to serve unsecured, unauthenticated access. Default 8080. It is assumed that firewall rules are set up such that this port is not reachable from outside of the cluster and that port 443 on the cluster's public address is proxied to this port. This is performed by nginx in the default setup. (default 8080)
      --kubelet-certificate-authority string                    Path to a cert file for the certificate authority.
      --kubelet-client-certificate string                       Path to a client cert file for TLS.
      --kubelet-client-key string                               Path to a client key file for TLS.
      --kubelet-https                                           Use https for kubelet connections. (default true)
      --kubelet-timeout duration                                Timeout for kubelet operations. (default 5s)
      --kubernetes-service-node-port int                        If non-zero, the Kubernetes master service (which apiserver creates/maintains) will be of type NodePort, using this as the value of the port. If zero, the Kubernetes master service will be of type ClusterIP.
      --long-running-request-regexp string                      A regular expression matching long running requests which should be excluded from maximum inflight request handling. (default "(/|^)((watch|proxy)(/|$)|(logs?|portforward|exec|attach)/?$)")
      --master-service-namespace string                         The namespace from which the kubernetes master services should be injected into pods. (default "default")
      --max-connection-bytes-per-sec int                        If non-zero, throttle each user connection to this number of bytes/sec. Currently only applies to long-running requests.
      --max-requests-inflight int                               The maximum number of requests in flight at a given time. When the server exceeds this, it rejects requests. Zero for no limit. (default 400)
      --min-request-timeout int                                 An optional field indicating the minimum number of seconds a handler must keep a request open before timing it out. Currently only honored by the watch request handler, which picks a randomized value above this number as the connection timeout, to spread out load. (default 1800)
      --oidc-ca-file string                                     If set, the OpenID server's certificate will be verified by one of the authorities in the oidc-ca-file, otherwise the host's root CA set will be used.
      --oidc-client-id string                                   The client ID for the OpenID Connect client, must be set if oidc-issuer-url is set.
      --oidc-groups-claim string                                If provided, the name of a custom OpenID Connect claim for specifying user groups. The claim value is expected to be an array of strings. This flag is experimental, please see the authentication documentation for further details.
      --oidc-issuer-url string                                  The URL of the OpenID issuer, only HTTPS scheme will be accepted. If set, it will be used to verify the OIDC JSON Web Token (JWT).
      --oidc-username-claim string                              The OpenID claim to use as the user name. Note that claims other than the default ('sub') is not guaranteed to be unique and immutable. This flag is experimental, please see the authentication documentation for further details. (default "sub")
      --profiling                                               Enable profiling via web interface host:port/debug/pprof/ (default true)
      --repair-malformed-updates                                If true, server will do its best to fix the update request to pass the validation, e.g., setting empty UID in update request to its existing value. This flag can be turned off after we fix all the clients that send malformed updates. (default true)
      --runtime-config value                                    A set of key=value pairs that describe runtime configuration that may be passed to apiserver. apis/<groupVersion> key can be used to turn on/off specific api versions. apis/<groupVersion>/<resource> can be used to turn on/off specific resources. api/all and api/legacy are special keys to control all and legacy api versions respectively.
      --secure-port int                                         The port on which to serve HTTPS with authentication and authorization. If 0, don't serve HTTPS at all. (default 6443)
      --service-account-key-file string                         File containing PEM-encoded x509 RSA private or public key, used to verify ServiceAccount tokens. If unspecified, --tls-private-key-file is used.
      --service-account-lookup                                  If true, validate ServiceAccount tokens exist in etcd as part of authentication.
      --service-cluster-ip-range value                          A CIDR notation IP range from which to assign service cluster IPs. This must not overlap with any IP ranges assigned to nodes for pods.
      --service-node-port-range value                           A port range to reserve for services with NodePort visibility. Example: '30000-32767'. Inclusive at both ends of the range. (default 30000-32767)
      --ssh-keyfile string                                      If non-empty, use secure SSH proxy to the nodes, using this user keyfile
      --ssh-user string                                         If non-empty, use secure SSH proxy to the nodes, using this user name
      --storage-backend string                                  The storage backend for persistence. Options: 'etcd2' (default), 'etcd3'.
      --storage-media-type string                               The media type to use to store objects in storage. Defaults to application/json. Some resources may only support a specific media type and will ignore this setting. (default "application/json")
      --storage-versions string                                 The per-group version to store resources in. Specified in the format "group1/version1,group2/version2,...". In the case where objects are moved from one group to the other, you may specify the format "group1=group2/v1beta1,group3/v1beta1,...". You only need to pass the groups you wish to change from the defaults. It defaults to a list of preferred versions of all registered groups, which is derived from the KUBE_API_VERSIONS environment variable. (default "apps/v1alpha1,authentication.k8s.io/v1beta1,authorization.k8s.io/v1beta1,autoscaling/v1,batch/v1,certificates/v1alpha1,componentconfig/v1alpha1,extensions/v1beta1,imagepolicy.k8s.io/v1alpha1,policy/v1alpha1,rbac.authorization.k8s.io/v1alpha1,v1")
      --target-ram-mb int                                       Memory limit for apiserver in MB (used to configure sizes of caches, etc.)
      --tls-cert-file string                                    File containing x509 Certificate for HTTPS. (CA cert, if any, concatenated after server cert). If HTTPS serving is enabled, and --tls-cert-file and --tls-private-key-file are not provided, a self-signed certificate and key are generated for the public address and saved to /var/run/kubernetes.
      --tls-private-key-file string                             File containing x509 private key matching --tls-cert-file.
      --token-auth-file string                                  If set, the file that will be used to secure the secure port of the API server via token authentication.
      --watch-cache                                             Enable watch caching in the apiserver (default true)
      --watch-cache-sizes value                                 List of watch cache sizes for every resource (pods, nodes, etc.), comma separated. The individual override format: resource#size, where size is a number. It takes effect when watch-cache is enabled. (default [])
```

###### Auto generated by spf13/cobra on 2-Sep-2016






<!-- BEGIN MUNGE: GENERATED_ANALYTICS -->
[![Analytics](https://kubernetes-site.appspot.com/UA-36037335-10/GitHub/docs/admin/kube-apiserver.md?pixel)]()
<!-- END MUNGE: GENERATED_ANALYTICS -->
