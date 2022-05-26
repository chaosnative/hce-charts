# hce

![Version: 2.8.2](https://img.shields.io/badge/Version-2.8.2-informational?style=flat-square) ![AppVersion: 2.8.0](https://img.shields.io/badge/AppVersion-2.8.0-informational?style=flat-square)

A Helm chart to install Harness Chaos Enterprise

**Homepage:** <https://harness.io>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Raj Babu Das | <rajbabu.das@harness.io> |  |
| Vedant Shrotria | <vedant.shrotria@harness.io> |  |
| Adarsh Kumar | <adarsh.kumar@harness.io> |  |

## Source Code

* <https://github.com/chaosnative/hce>

## Requirements

Kubernetes: `>=1.16.0-0`

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| adminConfig.DBPASSWORD | string | `"1234"` |  |
| adminConfig.DBUSER | string | `"admin"` |  |
| adminConfig.DB_PORT | string | `"27017"` |  |
| adminConfig.DB_SERVER | string | `""` | leave empty if uses Mongo DB deployed by this chart |
| adminConfig.JWTSecret | string | `"litmus-portal@123"` |  |
| adminConfig.VERSION | string | `"2.8.0"` |  |
| customLabels | object | `{}` | Additional labels |
| image.imagePullSecrets | list | `[]` |  |
| image.imageRegistryName | string | `"chaosnative"` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.host.name | string | `""` | This is ingress hostname (ex: my-domain.com) |
| ingress.host.paths.backend | string | `"/backend/(.*)"` | You may need adapt the path depending your ingress-controller |
| ingress.host.paths.frontend | string | `"/(.*)"` | You may need adapt the path depending your ingress-controller |
| ingress.name | string | `"litmus-ingress"` |  |
| ingress.tls | list | `[]` |  |
| mongo.affinity | object | `{}` |  |
| mongo.containerPort | int | `27017` |  |
| mongo.customLabels | object | `{}` |  |
| mongo.image.pullPolicy | string | `"Always"` |  |
| mongo.image.repository | string | `"mongo"` |  |
| mongo.image.tag | string | `"4.2.8"` |  |
| mongo.livenessProbe.failureThreshold | int | `5` |  |
| mongo.livenessProbe.initialDelaySeconds | int | `30` |  |
| mongo.livenessProbe.periodSeconds | int | `10` |  |
| mongo.livenessProbe.successThreshold | int | `1` |  |
| mongo.livenessProbe.timeoutSeconds | int | `5` |  |
| mongo.nodeSelector | object | `{}` |  |
| mongo.persistence.accessMode | string | `"ReadWriteOnce"` |  |
| mongo.persistence.size | string | `"20Gi"` |  |
| mongo.readinessProbe.initialDelaySeconds | int | `5` |  |
| mongo.readinessProbe.periodSeconds | int | `10` |  |
| mongo.readinessProbe.successThreshold | int | `1` |  |
| mongo.readinessProbe.timeoutSeconds | int | `1` |  |
| mongo.replicas | int | `1` |  |
| mongo.resources.limits.cpu | string | `"500m"` |  |
| mongo.resources.limits.ephemeral-storage | string | `"1Gi"` |  |
| mongo.resources.limits.memory | string | `"1Gi"` |  |
| mongo.resources.requests.cpu | string | `"250m"` |  |
| mongo.resources.requests.ephemeral-storage | string | `"500Mi"` |  |
| mongo.resources.requests.memory | string | `"500Mi"` |  |
| mongo.service.port | int | `27017` |  |
| mongo.service.targetPort | int | `27017` |  |
| mongo.service.type | string | `"ClusterIP"` |  |
| mongo.tolerations | list | `[]` |  |
| nameOverride | string | `""` |  |
| openshift.route.annotations | object | `{}` |  |
| openshift.route.enabled | bool | `false` |  |
| openshift.route.host | string | `""` |  |
| openshift.route.name | string | `"litmus-portal"` |  |
| portal.authServer.affinity | object | `{}` |  |
| portal.authServer.customLabels | object | `{}` |  |
| portal.authServer.env.ADMIN_PASSWORD | string | `"litmus"` |  |
| portal.authServer.env.ADMIN_USERNAME | string | `"admin"` |  |
| portal.authServer.env.STRICT_PASSWORD_POLICY | string | `"false"` |  |
| portal.authServer.image.pullPolicy | string | `"Always"` |  |
| portal.authServer.image.repository | string | `"hce-auth-server"` |  |
| portal.authServer.image.tag | string | `"2.8.0"` |  |
| portal.authServer.nodeSelector | object | `{}` |  |
| portal.authServer.replicas | int | `1` |  |
| portal.authServer.resources.limits.cpu | string | `"250m"` |  |
| portal.authServer.resources.limits.ephemeral-storage | string | `"1Gi"` |  |
| portal.authServer.resources.limits.memory | string | `"512Mi"` |  |
| portal.authServer.resources.requests.cpu | string | `"250m"` |  |
| portal.authServer.resources.requests.ephemeral-storage | string | `"500Mi"` |  |
| portal.authServer.resources.requests.memory | string | `"300Mi"` |  |
| portal.authServer.rpcContainerPort | int | `3030` |  |
| portal.authServer.serverContainerPort | int | `3000` |  |
| portal.authServer.service.authRPCServer.port | int | `3030` |  |
| portal.authServer.service.authRPCServer.targetPort | int | `3030` |  |
| portal.authServer.service.authServer.port | int | `9003` |  |
| portal.authServer.service.authServer.targetPort | int | `3000` |  |
| portal.authServer.service.type | string | `"NodePort"` |  |
| portal.authServer.serviceAccountName | string | `"default"` |  |
| portal.authServer.tolerations | list | `[]` |  |
| portal.authServer.updateStrategy | object | `{}` |  |
| portal.frontend.affinity | object | `{}` |  |
| portal.frontend.containerPort | int | `8080` |  |
| portal.frontend.customLabels | object | `{}` |  |
| portal.frontend.image.pullPolicy | string | `"Always"` |  |
| portal.frontend.image.repository | string | `"hce-frontend"` |  |
| portal.frontend.image.tag | string | `"2.8.0"` |  |
| portal.frontend.livenessProbe.failureThreshold | int | `5` |  |
| portal.frontend.livenessProbe.initialDelaySeconds | int | `30` |  |
| portal.frontend.livenessProbe.periodSeconds | int | `10` |  |
| portal.frontend.livenessProbe.successThreshold | int | `1` |  |
| portal.frontend.livenessProbe.timeoutSeconds | int | `5` |  |
| portal.frontend.nodeSelector | object | `{}` |  |
| portal.frontend.readinessProbe.initialDelaySeconds | int | `5` |  |
| portal.frontend.readinessProbe.periodSeconds | int | `10` |  |
| portal.frontend.readinessProbe.successThreshold | int | `1` |  |
| portal.frontend.readinessProbe.timeoutSeconds | int | `1` |  |
| portal.frontend.replicas | int | `1` |  |
| portal.frontend.resources.limits.cpu | string | `"250m"` |  |
| portal.frontend.resources.limits.ephemeral-storage | string | `"1Gi"` |  |
| portal.frontend.resources.limits.memory | string | `"512Mi"` |  |
| portal.frontend.resources.requests.cpu | string | `"250m"` |  |
| portal.frontend.resources.requests.ephemeral-storage | string | `"500Mi"` |  |
| portal.frontend.resources.requests.memory | string | `"300Mi"` |  |
| portal.frontend.service.port | int | `9091` |  |
| portal.frontend.service.targetPort | int | `8080` |  |
| portal.frontend.service.type | string | `"NodePort"` |  |
| portal.frontend.tolerations | list | `[]` |  |
| portal.frontend.updateStrategy | object | `{}` |  |
| portal.frontend.virtualService.enabled | bool | `false` |  |
| portal.frontend.virtualService.gateways | list | `[]` |  |
| portal.frontend.virtualService.hosts | list | `[]` |  |
| portal.frontend.virtualService.pathPrefixEnabled | bool | `false` |  |
| portal.graphqlServer.affinity | object | `{}` |  |
| portal.graphqlServer.customLabels | object | `{}` |  |
| portal.graphqlServer.genericEnv.AGENT_DEPLOYMENTS | string | `"[\"app=chaos-exporter\", \"name=chaos-operator\", \"app=event-tracker\", \"app=workflow-controller\"]"` |  |
| portal.graphqlServer.genericEnv.CONTAINER_RUNTIME_EXECUTOR | string | `"k8sapi"` |  |
| portal.graphqlServer.genericEnv.HUB_BRANCH_NAME | string | `"v2.8.x"` |  |
| portal.graphqlServer.genericEnv.LITMUS_CORE_VERSION | string | `"2.8.0"` |  |
| portal.graphqlServer.genericEnv.REMOTE_HUB_MAX_SIZE | string | `"5000000"` |  |
| portal.graphqlServer.genericEnv.SELF_CLUSTER | string | `"true"` |  |
| portal.graphqlServer.image.pullPolicy | string | `"Always"` |  |
| portal.graphqlServer.image.repository | string | `"hce-server"` |  |
| portal.graphqlServer.image.tag | string | `"2.8.0"` |  |
| portal.graphqlServer.imageEnv.ARGO_WORKFLOW_CONTROLLER_IMAGE | string | `"chaosnative/workflow-controller:v3.2.3"` |  |
| portal.graphqlServer.imageEnv.ARGO_WORKFLOW_EXECUTOR_IMAGE | string | `"chaosnative/argoexec:v3.2.3"` |  |
| portal.graphqlServer.imageEnv.EVENT_TRACKER_IMAGE | string | `"chaosnative/hce-event-tracker:2.8.0"` |  |
| portal.graphqlServer.imageEnv.LITMUS_CHAOS_EXPORTER_IMAGE | string | `"chaosnative/chaos-exporter:2.8.0"` |  |
| portal.graphqlServer.imageEnv.LITMUS_CHAOS_OPERATOR_IMAGE | string | `"chaosnative/chaos-operator:2.8.0"` |  |
| portal.graphqlServer.imageEnv.LITMUS_CHAOS_RUNNER_IMAGE | string | `"chaosnative/chaos-runner:2.8.0"` |  |
| portal.graphqlServer.imageEnv.SUBSCRIBER_IMAGE | string | `"chaosnative/hce-subscriber:2.8.0"` |  |
| portal.graphqlServer.livenessProbe.failureThreshold | int | `5` |  |
| portal.graphqlServer.livenessProbe.initialDelaySeconds | int | `30` |  |
| portal.graphqlServer.livenessProbe.periodSeconds | int | `10` |  |
| portal.graphqlServer.livenessProbe.successThreshold | int | `1` |  |
| portal.graphqlServer.livenessProbe.timeoutSeconds | int | `5` |  |
| portal.graphqlServer.nodeSelector | object | `{}` |  |
| portal.graphqlServer.readinessProbe.initialDelaySeconds | int | `5` |  |
| portal.graphqlServer.readinessProbe.periodSeconds | int | `10` |  |
| portal.graphqlServer.readinessProbe.successThreshold | int | `1` |  |
| portal.graphqlServer.readinessProbe.timeoutSeconds | int | `1` |  |
| portal.graphqlServer.replicas | int | `1` |  |
| portal.graphqlServer.resources.limits.cpu | string | `"512m"` |  |
| portal.graphqlServer.resources.limits.ephemeral-storage | string | `"1Gi"` |  |
| portal.graphqlServer.resources.limits.memory | string | `"1Gi"` |  |
| portal.graphqlServer.resources.requests.cpu | string | `"125m"` |  |
| portal.graphqlServer.resources.requests.ephemeral-storage | string | `"500Mi"` |  |
| portal.graphqlServer.resources.requests.memory | string | `"350Mi"` |  |
| portal.graphqlServer.rpcContainerPort | int | `8000` |  |
| portal.graphqlServer.serverContainerPort | int | `8080` |  |
| portal.graphqlServer.service.graphqlRPCServer.port | int | `8000` |  |
| portal.graphqlServer.service.graphqlRPCServer.targetPort | int | `8000` |  |
| portal.graphqlServer.service.graphqlServer.port | int | `9002` |  |
| portal.graphqlServer.service.graphqlServer.targetPort | int | `8080` |  |
| portal.graphqlServer.service.type | string | `"NodePort"` |  |
| portal.graphqlServer.serviceAccountName | string | `"litmus-server-account"` |  |
| portal.graphqlServer.tolerations | list | `[]` |  |
| portal.graphqlServer.updateStrategy | object | `{}` |  |
| portal.licenseServer.affinity | object | `{}` |  |
| portal.licenseServer.containerPort | int | `8080` |  |
| portal.licenseServer.image.pullPolicy | string | `"Always"` |  |
| portal.licenseServer.image.repository | string | `"hce-license-module"` |  |
| portal.licenseServer.image.tag | string | `"2.8.0"` |  |
| portal.licenseServer.nodeSelector | object | `{}` |  |
| portal.licenseServer.resources.limits.cpu | string | `"250m"` |  |
| portal.licenseServer.resources.limits.ephemeral-storage | string | `"1Gi"` |  |
| portal.licenseServer.resources.limits.memory | string | `"512Mi"` |  |
| portal.licenseServer.resources.requests.cpu | string | `"250m"` |  |
| portal.licenseServer.resources.requests.ephemeral-storage | string | `"500Mi"` |  |
| portal.licenseServer.resources.requests.memory | string | `"300Mi"` |  |
| portal.licenseServer.service.licenseServer.port | int | `80` |  |
| portal.licenseServer.service.licenseServer.targetPort | int | `8080` |  |
| portal.licenseServer.service.type | string | `"NodePort"` |  |
| portal.licenseServer.serviceAccountName | string | `"litmus-server-account"` |  |
| portal.licenseServer.tolerations | list | `[]` |  |
| portal.waitForMongodb.image.pullPolicy | string | `"Always"` |  |
| portal.waitForMongodb.image.repository | string | `"curl"` |  |
| portal.waitForMongodb.image.tag | string | `"2.8.0"` |  |
| portal.waitForMongodb.resources.limits.cpu | string | `"250m"` |  |
| portal.waitForMongodb.resources.limits.ephemeral-storage | string | `"200Mi"` |  |
| portal.waitForMongodb.resources.limits.memory | string | `"200Mi"` |  |
| portal.waitForMongodb.resources.requests.cpu | string | `"125m"` |  |
| portal.waitForMongodb.resources.requests.ephemeral-storage | string | `"100Mi"` |  |
| portal.waitForMongodb.resources.requests.memory | string | `"100Mi"` |  |
| portalScope | string | `"cluster"` |  |
| upgradeAgent.affinity | object | `{}` |  |
| upgradeAgent.controlPlane.image.pullPolicy | string | `"Always"` |  |
| upgradeAgent.controlPlane.image.repository | string | `"hce-upgrade-agent-cp"` |  |
| upgradeAgent.controlPlane.image.tag | string | `"2.8.0"` |  |
| upgradeAgent.nodeSelector | object | `{}` |  |
| upgradeAgent.tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.8.1](https://github.com/norwoodj/helm-docs/releases/v1.8.1)
