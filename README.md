# Redis Package

Redis(R) is an open source, advanced key-value store. It is often referred to as a data structure server since keys can contain strings, hashes, lists, sets and sorted sets.

## Configuration Reference

You can configure the following:

###  Redis® Image parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|image.registry|Redis® image registry|string|docker.io|
|image.repository|Redis® image repository|string|bitnami/redis|
|image.tag|Redis® image tag (immutable tags are recommended)|string|6.2.7-debian-11-r0|
|image.pullPolicy|Redis® image pull policy|string|IfNotPresent|
|image.debug|"Enable image debug mode"|string|false|

### Redis® common configuration parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|architecture|Redis® architecture. Allowed values: standalone or replication|string|replication|
|auth.enabled|Enable password authentication|string|true|
|auth.sentinel|Enable password authentication on sentinels too|string|true|
|auth.password|Redis® password|string|""|
|auth.existingSecret|The name of an existing secret with Redis® credentials|string|""|
|auth.existingSecretPasswordKey|Password key to be retrieved from existing secret|string|""|
|auth.usePasswordFiles|Mount credentials as files instead of using an environment variable|string|false|
|commonConfiguration|Common configuration to be added into the ConfigMap|string|""|
|existingConfigmap|The name of an existing ConfigMap with your custom configuration for Redis® nodes|string|""|

### Redis® master configuration parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|master.count|Number of Redis® master instances to deploy (experimental, requires additional configuration)|integer|1|	
|master.redisTls|master redisTls|string|"no"|
|master.bitnamiDebug|master. bitnamiDebug|string|"false"|
|master.redisReplicationmode|master.redisReplicationmode|string|slave|
|master.allowEmptypassword|master.allowEmptypassword|string|"no"|
|master.redisMasterhost|master.redisMasterhost|string|redis-master-0.redis-headless.default.svc.cluster.local|
|master.redisMasterportnumber|master.redisMasterportnumber|integer|"6379"|
|master.redisPort|master.redisPort|integer|"6379"|
|master.egress.port|master.egress.port|integer|53|
|master.prometheusioport|master.prometheusioport|integer|"9121"|
|master.prometheusioscrape|master.prometheusioscrape|string|"true"|
|master.containerPorts.redis|"Container port to open on Redis® master nodes"|integer|6379|
|master.env.REDIS_ALIAS|master.env.REDIS_ALIAS|string|redis|
|master.env.REDIS_USER|master.env.REDIS_USER|string|default|
|master.env.REDIS_PASSWORD|master.env.REDIS_PASSWORD|string|redis-password|
|master.startupProbe.enabled|Enable startupProbe on Redis® master nodes|string|false| 
|master.startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|20|
|master.startupProbe.periodSeconds|Period seconds for startupProbe|integer|5|
|master.startupProbe.timeoutSeconds|Timeout seconds for startupProbe|integer|5|
|master.startupProbe.failureThreshold|Failure threshold for startupProbe|integer|5|
|master.startupProbe.successThreshold|Success threshold for startupProbe|integer|1|
|master.livenessProbe.enabled|Enable livenessProbe on Redis® master nodes|string|true|
|master.livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|20|
|master.livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|5|
|master.livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|master.livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|5|
|master.livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|master.readinessProbe.enabled|Enable readinessProbe on Redis® master nodes|string|true|
|master.readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|20|
|master.readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|5|
|master.readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|1|
|master.readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|5|
|master.readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|master.customStartupProbe|Custom startupProbe that overrides the default one|string|{}|
|master.customLivenessProbe|Custom livenessProbe that overrides the default one|string|{}|
|master.customReadinessProbe|Custom readinessProbe that overrides the default one|string|{}|
|master.resources.limits|The resources limits for the Redis® master containers|string|{}|
|master.resources.requests|The requested resources for the Redis® master containers|string|{}|
|master.podSecurityContext.enabled|Enabled Redis® master pods' Security Context|string|true|
|master.podSecurityContext.fsGroup|Set Redis® master pod's Security Context fsGroup|integer|1001|
|master.containerSecurityContext.enabled|Enabled Redis® master containers' Security Context|string|true|
|master.containerSecurityContext.runAsUser|Set Redis® master containers' Security Context runAsUser|integer|1001|
|master.kind|Use either Deployment or StatefulSet (default)|string|StatefulSet|
|master.schedulerName|Alternate scheduler for Redis® master pods|string|""|
|master.updateStrategy.type|Redis® master statefulset strategy type|string|RollingUpdate|
|master.priorityClassName|Redis® master pods' priorityClassName|string|""|
|master.podLabels|Extra labels for Redis® master pods|string|{}|
|master.podAnnotations|Annotations for Redis® master pods|string|{}|
|master.shareProcessNamespace|Share a single process namespace between all of the containers in Redis® master pods|string|false|
|master.podAffinityPreset|Pod affinity preset. Ignored if master.affinity is set. Allowed values: soft or	hard|string|""|
|master.podAntiAffinityPreset|Pod anti-affinity preset. Ignored if 	string	soft master.affinity is set. Allowed values: soft or hard|string|soft|			
|master.nodeAffinityPreset.type|Node affinity preset type. Ignored if master.affinity	is set. Allowed values: 	soft	or hard|string|""|	
|master.nodeAffinityPreset.key|Node label key to match. Ignored if master.affinity  is set|string|""|
|master.affinity|Affinity for Redis® master pods assignment|string|{}|
|master.nodeSelector|Node labels for Redis® master pods assignment|string|{}|
|master.dnsPolicy|DNS Policy for Redis® master pod|string|""|
|master.dnsConfig|DNS Configuration for Redis® master pod|string|{}|
|master.lifecycleHooks|for the Redis® master container(s) to automate configuration before or after startup|string|{}|
|master.persistence.enabled|Enable persistence on Redis® master nodes using Persistent Volume Claims|string|true|
|master.persistence.medium|Provide a medium for emptyDir  volumes.|string|""|	
|master.persistence.sizeLimit|Set this to enable a size limit for emptyDir volumes.|string|""|	
|master.persistence.path|The path the volume will be mounted at on Redis® master containers|string|/data|
|master.persistence.subPath|The subdirectory of the volume to mount on Redis® master containers|string|""|
|master.persistence.storageClass|Persistent Volume storage class|string|""|
|master.persistence.accessModes|Persistent Volume access modes|string|["ReadWriteOnce"]|
|master.persistence.size|Persistent Volume size|string|8Gi|
|master.persistence.annotations|Additional custom annotations for the PVC|string|{}|
|master.persistence.selector|Additional labels to match for the PVC|string|{}|
|master.persistence.dataSource|Custom PVC data source|string|{}|
|master.persistence.existingClaim|Use a existing PVC which must be created manually before bound|string|""|
|master.service.type|Redis® master service type|string|ClusterIP|
|master.service.externalTrafficPolicy|Redis® master service external traffic policy|string|Cluster|
|master.service.internalTrafficPolicy|Redis® master service internal traffic policy (requires Kubernetes v1.22 or greater to be usable)|string|Cluster|
|master.service.clusterIP|Redis® master service Cluster IP|string|""|
|master.service.loadBalancerIP|Redis® master service Load Balancer IP|string|""|
|master.service.annotations|Additional custom annotations for Redis® master service|string|{}|
|master.terminationGracePeriodSeconds|Integer setting the termination grace period for the redis-master pods|integer|30|
			
### Redis® replicas configuration parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|replica.replicaCount|Number of Redis® replicas to deploy|integer|3|
|replica.configuration|Configuration for Redis® replicas nodes|string|""|
|replica.disableCommands|Array with Redis® commands to disable on replicas nodes|string|["FLUSHDB","FLUSHALL"]|
|replica.extraEnvVarsCM|Name of existing ConfigMap containing extra env vars for Redis® replicas nodes|string|""|
|replica.extraEnvVarsSecret|Name of existing Secret containing extra env vars for Redis® replicas nodes|string|""|
|replica.externalMaster.enabled|Use external master for bootstrapping|string|false|
|replica.externalMaster.host|External master host to bootstrap from|string|""|
|replica.externalMaster.port|Port for Redis service external master host|integer|6379|
|replica.containerPorts.redis|Container port to open on Redis® replicas nodes|integer|6379|
|replica.env.REDIS_ALIAS|replica.env.REDIS_ALIAS|string|redis|
|replica.env.REDIS_USER|replica.env.REDIS_USER|string|default|
|replica.env.REDIS_PASSWORD|replica.env.REDIS_PASSWORD|string|redis-password|
|replica.annotations.prometheusioport|replica.annotations.prometheusioport|string|"9121"|
|replica.annotations.prometheusioscrape|replica.annotations.prometheusioscrape|string|"true"|
|replica.startupProbe.enabled|Enable startupProbe on Redis® replicas nodes|string|true|
|replica.startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|10|
|replica.startupProbe.periodSeconds|Period seconds for startupProbe|integer|10|
|replica.startupProbe.timeoutSeconds|Timeout seconds for startupProbe|integer|5|
|replica.startupProbe.failureThreshold|Failure threshold for startupProbe|integer|22|
|replica.startupProbe.successThreshold|Success threshold for startupProbe|integer|1|
|replica.livenessProbe.enabled|Enable livenessProbe on Redis® replicas nodes|string|true|
|replica.livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|20|
|replica.livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|5|
|replica.livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|replica.livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|5|
|replica.livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|replica.readinessProbe.enabled|Enable readinessProbe on Redis® replicas nodes|string|true|
|replica.readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|20|
|replica.readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|5|
|replica.readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|1|
|replica.readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|5|
|replica.readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|replica.customStartupProbe|Custom startupProbe that overrides the default one|string|{}|
|replica.customLivenessProbe|Custom livenessProbe that overrides the default one|string|{}|
|replica.customReadinessProbe|Custom readinessProbe that overrides the default one|string|{}|
|replica.resources.limits|The resources limits for the Redis® replicas containers|string|{}|
|replica.resources.requests|The requested resources for the Redis® replicas containers|string|{}|
|replica.podSecurityContext.enabled|Enabled Redis® replicas pods' Security Context|string|true|
|replica.podSecurityContext.fsGroup|Set Redis® replicas pod's Security Context fsGroup|integer|1001|
|replica.containerSecurityContext.enabled|Enabled Redis® replicas containers' Security Context|string|true|
|replica.containerSecurityContext.runAsUser|Set Redis® replicas containers' Security Context runAsUser|integer|1001|
|replica.schedulerName|Alternate scheduler for Redis® replicas pods|string|""|
|replica.updateStrategy.type|Redis® replicas statefulset strategy type|string|RollingUpdate|
|replica.priorityClassName|Redis® replicas pods' priorityClassName|string|""|
|replica.podManagementPolicy|podManagementPolicy to manage scaling operation of %%MAIN_CONTAINER_NAME%% pods|string|""|
|replica.podLabels|Extra labels for Redis® replicas pods|string|{}|
|replica.podAnnotations|Annotations for Redis® replicas pods|string|{}|
|replica.shareProcessNamespace|Share a single process namespace between all of the containers in Redis® replicas pods|string|false|
|replica.podAffinityPreset|Pod affinity preset. Ignored if replica.affinity 	 is set. Allowed values: soft or hard|string|""|	
|replica.podAntiAffinityPreset|Pod anti-affinity preset. Ignored if replica.affinity is set. Allowed values: soft or hard|string|soft|
|replica.nodeAffinityPreset.type|Node affinity preset type. Ignored if replica.affinity	 is set. Allowed values: soft or hard|string|""|
|replica.nodeAffinityPreset.key|Node label key to match. Ignored if replica.affinity is set|string|""|
|replica.affinity|Affinity for Redis® replicas pods assignment|string|""|
|replica.nodeSelector|Node labels for Redis® replicas pods assignment|string|{}|
|replica.dnsPolicy|NS Policy for Redis® replica pods|string|""|
|replica.dnsConfig|DNS Configuration for Redis® replica pods|string|{}|
|replica.lifecycleHooks|for the Redis® replica container(s) to automate configuration before or after startup|string|{}|
|replica.persistence.enabled|Enable persistence on Redis® replicas nodes using Persistent Volume Claims|string|true|
|replica.persistence.medium|Provide a medium for emptyDir	 volumes.|string|""|
|replica.persistence.sizeLimit|Set this to enable a size limit for emptyDir volumes.|string|""|
|replica.persistence.path|The path the volume will be mounted at on Redis® replicas containers|string|/data|
|replica.persistence.subPath|The subdirectory of the volume to mount on Redis® replicas containers|string|""|
|replica.persistence.storageClass|Persistent Volume storage class|string|""|
|replica.persistence.accessModes|Persistent Volume access modes|string|["ReadWriteOnce"]|
|replica.persistence.size|Persistent Volume size|string|8Gi|
|replica.persistence.annotations|Additional custom annotations for the PVC|string|{}|
|replica.persistence.selector|Additional labels to match for the PVC|string|{}|
|replica.persistence.dataSource|Custom PVC data source|string|{}|
|replica.service.type|Redis® replicas service type|string|ClusterIP|
|replica.service.externalTrafficPolicy|Redis® replicas service external traffic policy|string|Cluster|
|replica.service.internalTrafficPolicy|Redis® replicas service internal traffic policy (requires Kubernetes v1.22 or greater to be usable)|string|Cluster|
|replica.service.clusterIP|Redis® replicas service Cluster IP|string|""|
|replica.service.loadBalancerIP|Redis® replicas service Load Balancer IP|string|""|
|replica.service.annotations|Additional custom annotations for Redis® replicas service|string|{}|
|replica.terminationGracePeriodSeconds|Integer setting the termination grace period for the redis-replicas pods|integer|30|                                              |replica.autoscaling.enabled|Enable replica autoscaling settings	string|false| 
|replica.autoscaling.minReplicas|Minimum replicas for the pod autoscaling|integer|1|
|replica.autoscaling.maxReplicas|Maximum replicas for the pod autoscaling|integer|11|
|replica.autoscaling.targetCPU|Percentage of CPU to consider when autoscaling|string|""|
|replica.autoscaling.targetMemory|Percentage of Memory to consider when autoscaling|string|""|


### Redis® Sentinel configuration parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|sentinel.containerPorts.sentinel|Container port to open on Redis® Sentinel nodes|integer|26379|
|sentinel.service.ports.sentinel|Redis® service port for Redis® Sentinel|integer|26379|
|sentinel.service.nodePorts.sentinel|Node port for Sentinel|string|""|

### Other Parameters
 
|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|networkPolicy.enabled|Enable creation of NetworkPolicy resources|string|false|
|networkPolicy.allowExternal|Don't require client label for connections|string|true
|networkPolicy.ingressNSMatchLabels|Labels to match to allow traffic from other namespaces|string|{}|
|networkPolicy.ingressNSPodMatchLabels|Pod labels to match to allow traffic from other namespaces|string|{}|
|podSecurityPolicy.create|Whether to create a PodSecurityPolicy. WARNING: PodSecurityPolicy is deprecated in Kubernetes v1.21 or later, unavailable in v1.25 or later|string|false|
|podSecurityPolicy.enabled|Enable PodSecurityPolicy's RBAC rules|string|false|
|rbac.create|Specifies whether RBAC resources should be created|string|false|
|serviceAccount.create|Specifies whether a ServiceAccount should be created|string|true|
|serviceAccount.name|The name of the ServiceAccount to use.|string|""|
|serviceAccount.automountServiceAccountToken|Whether to auto mount the service account token|string|true|
|serviceAccount.annotations|Additional custom annotations for the ServiceAccount|string|{}|
|pdb.create	Specifies|whether a PodDisruptionBudget should be created|string|false|
|pdb.minAvailable|Min number of pods that must still be available after the eviction|integer|1|
|pdb.maxUnavailable|Max number of pods that can be unavailable after the eviction|string|""|
|tls.enabled|Enable TLS traffic|string|false|
|tls.authClients|Require clients to authenticate|string|true|
|tls.autoGenerated|Enable autogenerated certificates|string|false|
|tls.existingSecret|The name of the existing secret that contains the TLS certificates|string|""|
|tls.certificatesSecret|DEPRECATED. Use existingSecret instead.|string|""|
|tls.certFilename|Certificate filename|string|""|
|tls.certKeyFilename|Certificate Key filename|string|""|
|tls.certCAFilename|CA Certificate filename|string|""|
|tls.dhParamsFilename|File containing DH params (in order to support DH based ciphers)|string|""|


### Metrics Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|metrics.enabled|Start a sidecar prometheus exporter to expose Redis® metrics|string|false|
|metrics.image.registry|Redis® Exporter image registry|string|docker.io|
|metrics.image.repository|Redis® Exporter image repository|string|bitnami/redis-exporter|
|metrics.image.tag|Redis® Redis® Exporter image tag (immutable tags are recommended)|string|1.39.0-debian-11-r0|
|metrics.image.pullPolicy|Redis® Exporter image pull policy|string|IfNotPresent|
|metrics.redisTargetHost|A way to specify an alternative Redis® hostname|string|localhost|
|metrics.extraArgs|Extra arguments for Redis® exporter, for example:|string|{}|
|metrics.containerSecurityContext.enabled|Enabled Redis® exporter containers' Security Context|string|true|
|metrics.containerSecurityContext.runAsUser|Set Redis® exporter containers' Security Context runAsUser|integer|1001|
|metrics.resources.limits|The resources limits for the Redis® exporter container|string|{}|
|metrics.resources.requests|The requested resources for the Redis® exporter container|string|{}|
|metrics.podLabels|Extra labels for Redis® exporter pods|string|{}|
|metrics.podAnnotations|Annotations for Redis® exporter pods|string|{}|
|metrics.service.type|Redis® exporter service type|string|ClusterIP|
|metrics.service.port|Redis® exporter service port|integer|9121|
|metrics.service.externalTrafficPolicy|Redis® exporter service external traffic policy|string|Cluster|
|metrics.service.loadBalancerIP|Redis® exporter service Load Balancer IP|string|""|
|metrics.service.annotations|Additional custom annotations for Redis® exporter service|string|{}|
|metrics.serviceMonitor.enabled|Create ServiceMonitor resource(s) for scraping metrics using PrometheusOperator|string|false|
|metrics.serviceMonitor.namespace|The namespace in which the ServiceMonitor will be created|string|""|
|metrics.serviceMonitor.interval|The interval at which metrics should be scraped|string|30s|
|metrics.serviceMonitor.scrapeTimeout|The timeout after which the scrape is ended|string|""|
|metrics.serviceMonitor.honorLabels|Specify honorLabels parameter to add the scrape endpoint|string|fasle|
|metrics.serviceMonitor.additionalLabels|Additional labels that can be used so ServiceMonitor resource(s) can be discovered by Prometheus|string|{}|
|metrics.prometheusRule.enabled|Create a custom prometheusRule Resource for scraping metrics using PrometheusOperator|string|false|
|metrics.prometheusRule.namespace|The namespace in which the prometheusRule will be created|string|""|
|metrics.prometheusRule.additionalLabels|Additional labels for the prometheusRule|string|{}|
			
### Init Container Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|volumePermissions.enabled|Enable init container that changes the owner/group of the PV mount point to runAsUser:fsGroup|string|false|
|volumePermissions.image.registry|Bitnami Shell image registry|string|docker.io|
|volumePermissions.image.repository|Bitnami Shell image repository|string|bitnami/bitnami-shell|
|volumePermissions.image.tag|Bitnami Shell image tag (immutable tags are recommended)|string|11-debian-11-r0|
|volumePermissions.image.pullPolicy|Bitnami Shell image pull policy|string|IfNotPresent|
|volumePermissions.resources.limits|The resources limits for the init container|string|{}|
|volumePermissions.resources.requests|The requested resources for the init container|string|{}|
|volumePermissions.containerSecurityContext.runAsUser|Set init container's Security Context runAsUser|integer|0|
|sysctl.enabled|Enable init container to modify Kernel settings|string|false|
|sysctl.image.registry|Bitnami Shell image registry|string|docker.io|
|sysctl.image.repository|Bitnami Shell image repository|string|bitnami/bitnami-shell|
|sysctl.image.tag|Bitnami Shell image tag (immutable tags are recommended)|string|11-debian-11-r0|
|sysctl.image.pullPolicy|Bitnami Shell image pull policy|string|IfNotPresent|
|sysctl.mountHostSys|Mount the host	/sys folder to	/host-sys|string|false|
|sysctl.resources.limits|The resources limits for the init container|string|{}|
|sysctl.resources.requests|The requested resources for the init container|string|{}|

### useExternalDNS Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|useExternalDNS.enabled|Enable various syntax that would enable external-dns to work. Note this requires a working installation of external-dns to be usable.|string|false|
|useExternalDNS.additionalAnnotations|Extra annotations to be utilized when	external-dns is enabled.|string|{}|
|useExternalDNS.annotationKey|The annotation key utilized when external-dns is enabled.|string|external-dns.alpha.kubernetes.io/|
|useExternalDNS.suffix|The DNS suffix utilized when external-dns	is enabled. Note that we prepend the suffix with the full name of the release.|string|""|
			





 
 
 
 
 
 
 
 
 
 
 
 
 

			
			









