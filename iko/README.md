# iko

![Version: 1.4.0](https://img.shields.io/badge/Version-1.4.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.3.0](https://img.shields.io/badge/AppVersion-1.3.0-informational?style=flat-square)

A Helm chart for Integraal Klant Objectbeeld (IKO)

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| autoscaling.targetMemoryUtilizationPercentage | string | `nil` |  |
| existingSecret | string | `nil` |  |
| extraConfigMaps | list | `[]` | List of ConfigMaps to create (when `extraConfigMapsEnabled=true`) and inject into the pod. Each entry supports: `name` (required), `mode` (env/mount/both, default: both), `mountPath` (default: /config/<name>), `data` (map of key → content). NOTE: env vars set elsewhere in this chart take precedence over values in a mounted application.yaml. Example: ```yaml - name: my-app-config   mode: both   mountPath: /app/config   data:     application.yaml: |       server.port: 8080 ``` |
| extraConfigMapsEnabled | bool | `true` | Set to false to reference pre-existing ConfigMaps without having the chart create them. |
| extraEnvVars | list | `[]` | Extra environment variables to inject into the container |
| extraVolumeMounts | list | `[]` | Additional volume mounts for the main container |
| extraVolumes | list | `[]` | Additional volumes to attach to the pod |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | Pull policy for the image |
| image.repository | string | `""` | Domain of the image repository |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"iko.example.com"` |  |
| ingress.hosts[0].paths[0].path | string | `"/admin"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| ingress.hosts[0].paths[1].path | string | `"/assets"` |  |
| ingress.hosts[0].paths[1].pathType | string | `"Prefix"` |  |
| ingress.hosts[0].paths[2].path | string | `"/oauth2"` |  |
| ingress.hosts[0].paths[2].pathType | string | `"Prefix"` |  |
| ingress.hosts[0].paths[3].path | string | `"/login/oauth2"` |  |
| ingress.hosts[0].paths[3].pathType | string | `"Prefix"` |  |
| ingress.tls | list | `[]` |  |
| livenessProbe.failureThreshold | int | `3` |  |
| livenessProbe.httpGet.path | string | `"/admin"` |  |
| livenessProbe.httpGet.port | string | `"admin-port"` |  |
| livenessProbe.initialDelaySeconds | int | `10` |  |
| livenessProbe.periodSeconds | int | `30` |  |
| livenessProbe.successThreshold | int | `1` |  |
| livenessProbe.timeoutSeconds | int | `1` |  |
| monitoring.podMonitor.enabled | bool | `false` |  |
| monitoring.podMonitor.interval | string | `""` | Interval between Prometheus scrapes |
| monitoring.podMonitor.scrapeTimeout | string | `""` | Scrape timeout for the PodMonitor |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| persistence.accessModes | list | `["ReadWriteOnce"]` | Access modes for the PVC |
| persistence.annotations | object | `{}` |  |
| persistence.enabled | bool | `false` | Enable/disable persistent volumes for iko |
| persistence.existingClaim | string | `nil` | persistence.existingClaim The name of an existing PVC to use for persistence |
| persistence.extraPvcLabels | object | `{}` | Extra labels to add to the PVC metadata |
| persistence.finalizers | list | `[]` | Finalizers to add to the PVC |
| persistence.mountPath | string | `"/tmp"` | persistence.mountPath Path to mount the volume at. |
| persistence.selectorLabels | object | `{}` | Additional selector labels for the PVC |
| persistence.size | string | `"1Gi"` | persistence.size Size of data volume |
| persistence.storageClassName | string | `""` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext.fsGroup | int | `1000` |  |
| ports[0].containerPort | int | `8080` |  |
| ports[0].name | string | `"admin-port"` |  |
| readinessProbe.failureThreshold | int | `3` |  |
| readinessProbe.httpGet.path | string | `"/admin"` |  |
| readinessProbe.httpGet.port | string | `"admin-port"` |  |
| readinessProbe.periodSeconds | int | `10` |  |
| readinessProbe.successThreshold | int | `1` |  |
| readinessProbe.timeoutSeconds | int | `1` |  |
| redis.affinity | object | `{}` |  |
| redis.enabled | bool | `true` | Enable/disable the bundled Redis deployment |
| redis.image.pullPolicy | string | `"IfNotPresent"` | Redis image pull policy |
| redis.image.repository | string | `"docker.io/redis"` | Redis image repository |
| redis.image.tag | string | `"8.4.0"` | Redis image tag |
| redis.nodeSelector | object | `{}` |  |
| redis.replicaCount | int | `1` | Number of Redis replicas |
| redis.resources.limits.cpu | string | `"250m"` |  |
| redis.resources.limits.memory | string | `"128Mi"` |  |
| redis.resources.requests.cpu | string | `"50m"` |  |
| redis.resources.requests.memory | string | `"64Mi"` |  |
| redis.service.port | int | `6379` | Port Redis listens on |
| redis.tolerations | list | `[]` |  |
| replicaCount | int | `1` | Amount of replicas running IKO |
| resources.limits.cpu | string | `"2000m"` |  |
| resources.limits.memory | string | `"2Gi"` |  |
| resources.requests.cpu | string | `"500m"` |  |
| resources.requests.memory | string | `"1536Mi"` |  |
| securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| securityContext.readOnlyRootFilesystem | bool | `false` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.runAsUser | int | `1000` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | If not set and create is true, a name is generated using the fullname template |
| settings.iko.cryptoKey | string | `""` | Or, if using existingSecret: `IKO_CRYPTO_KEY` |
| settings.iko.security.admin.authorities | string | `"ROLE_ADMIN"` | Required admin roles/authorities (comma-separated) |
| settings.iko.security.admin.rolesClaim | string | `"roles"` | Claim containing admin roles in OIDC login tokens |
| settings.iko.security.admin.session.timeout | string | `"30m"` | Admin session timeout duration. Must use Spring duration format (e.g., 30m, 1h). |
| settings.iko.security.admin.session.warningBefore | string | `"2m"` | Time before session expiry to show the timeout warning modal. |
| settings.iko.security.api.authoritiesClaim | string | `"resource_access.iko.roles"` | Claim containing API authorities in JWT access tokens |
| settings.iko.security.sessionCookieSecure | bool | `false` | Secure flag for session cookie (JSESSIONID and XSRF-TOKEN). Set to true when running behind HTTPS. |
| settings.iko.serverPort | int | `8080` | Port IKO listens on |
| settings.keycloak.authServerURL | string | `""` | URL of Keycloak - Required |
| settings.keycloak.clientID | string | `""` | Client-ID to connect with Keycloak |
| settings.keycloak.clientSecret | string | `""` | Or, if using existingSecret: `SPRING_SECURITY_OAUTH2_CLIENT_REGISTRATION_KEYCLOAKAPI_CLIENTSECRET` |
| settings.keycloak.realm | string | `""` | Keycloak realm - Required |
| settings.redis.host | string | `nil` |  |
| settings.redis.port | string | `nil` |  |
| settings.spring.datasource.driverClassName | string | `"org.postgresql.Driver"` | Driver for the postgresql database |
| settings.spring.datasource.password | string | `"TOPSECRET"` | Password for the postgresql database |
| settings.spring.datasource.url | string | `""` | URL for the postgresql database |
| settings.spring.datasource.username | string | `""` | Username for the postgresql database |
| settings.spring.jpa.properties.hibernateDialect | string | `"org.hibernate.dialect.PostgreSQLDialect"` |  |
| startupProbe.failureThreshold | int | `30` |  |
| startupProbe.httpGet.path | string | `"/admin"` |  |
| startupProbe.httpGet.port | string | `"admin-port"` |  |
| startupProbe.initialDelaySeconds | int | `5` |  |
| startupProbe.periodSeconds | int | `10` |  |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
