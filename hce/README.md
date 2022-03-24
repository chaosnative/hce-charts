# hce

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![AppVersion: 0.1.0](https://img.shields.io/badge/AppVersion-0.1.0-informational?style=flat-square)

A Helm chart to install Harness Chaos Enterprise

**Homepage:** <https://harness.io>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Raj Babu Das | rajbabu.das@harness.io |  |

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
| adminConfig.VERSION | string | `"master-ci"` |  |
| customLabels | object | `{}` | Additional labels |
| image.imagePullSecrets[0].name | string | `"regcred"` |  |
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
| portal.frontend.affinity | object | `{}` |  |
| portal.frontend.containerPort | int | `8080` |  |
| portal.frontend.customLabels | object | `{}` |  |
| portal.frontend.image.pullPolicy | string | `"Always"` |  |
| portal.frontend.image.repository | string | `"hce-frontend"` |  |
| portal.frontend.image.tag | string | `"master-ci"` |  |
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
| portal.frontend.resources.requests.cpu | string | `"25m"` |  |
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
| portal.server.affinity | object | `{}` |  |
| portal.server.authServer.containerPort | int | `3000` |  |
| portal.server.authServer.env.ADMIN_PASSWORD | string | `"litmus"` |  |
| portal.server.authServer.env.ADMIN_USERNAME | string | `"admin"` |  |
| portal.server.authServer.image.pullPolicy | string | `"Always"` |  |
| portal.server.authServer.image.repository | string | `"hce-auth-server"` |  |
| portal.server.authServer.image.tag | string | `"master-ci"` |  |
| portal.server.authServer.resources.limits.cpu | string | `"250m"` |  |
| portal.server.authServer.resources.limits.ephemeral-storage | string | `"1Gi"` |  |
| portal.server.authServer.resources.limits.memory | string | `"512Mi"` |  |
| portal.server.authServer.resources.requests.cpu | string | `"25m"` |  |
| portal.server.authServer.resources.requests.ephemeral-storage | string | `"500Mi"` |  |
| portal.server.authServer.resources.requests.memory | string | `"150Mi"` |  |
| portal.server.customLabels | object | `{}` |  |
| portal.server.graphqlServer.containerPort | int | `8080` |  |
| portal.server.graphqlServer.genericEnv.AGENT_DEPLOYMENTS | string | `"[\"app=chaos-exporter\", \"name=chaos-operator\", \"app=event-tracker\", \"app=workflow-controller\"]"` |  |
| portal.server.graphqlServer.genericEnv.CONTAINER_RUNTIME_EXECUTOR | string | `"k8sapi"` |  |
| portal.server.graphqlServer.genericEnv.EVENT_TRACKER_IMAGE | string | `"chaosnative/hce-event-tracker:master-ci"` |  |
| portal.server.graphqlServer.genericEnv.HUB_BRANCH_NAME | string | `"v2.2.x"` |  |
| portal.server.graphqlServer.genericEnv.SELF_CLUSTER | string | `"true"` |  |
| portal.server.graphqlServer.genericEnv.SUBSCRIBER_IMAGE | string | `"chaosnative/hce-subscriber:master-ci"` |  |
| portal.server.graphqlServer.image.pullPolicy | string | `"Always"` |  |
| portal.server.graphqlServer.image.repository | string | `"hce-server"` |  |
| portal.server.graphqlServer.image.tag | string | `"master-ci"` |  |
| portal.server.graphqlServer.imageEnv.ARGO_WORKFLOW_CONTROLLER_IMAGE | string | `"litmuschaos/workflow-controller:v2.11.0"` |  |
| portal.server.graphqlServer.imageEnv.ARGO_WORKFLOW_EXECUTOR_IMAGE | string | `"litmuschaos/argoexec:v2.11.0"` |  |
| portal.server.graphqlServer.imageEnv.LITMUS_CHAOS_EXPORTER_IMAGE | string | `"litmuschaos/chaos-exporter:2.3.0"` |  |
| portal.server.graphqlServer.imageEnv.LITMUS_CHAOS_OPERATOR_IMAGE | string | `"litmuschaos/chaos-operator:2.3.0"` |  |
| portal.server.graphqlServer.imageEnv.LITMUS_CHAOS_RUNNER_IMAGE | string | `"litmuschaos/chaos-runner:2.3.0"` |  |
| portal.server.graphqlServer.livenessProbe.failureThreshold | int | `5` |  |
| portal.server.graphqlServer.livenessProbe.initialDelaySeconds | int | `30` |  |
| portal.server.graphqlServer.livenessProbe.periodSeconds | int | `10` |  |
| portal.server.graphqlServer.livenessProbe.successThreshold | int | `1` |  |
| portal.server.graphqlServer.livenessProbe.timeoutSeconds | int | `5` |  |
| portal.server.graphqlServer.readinessProbe.initialDelaySeconds | int | `5` |  |
| portal.server.graphqlServer.readinessProbe.periodSeconds | int | `10` |  |
| portal.server.graphqlServer.readinessProbe.successThreshold | int | `1` |  |
| portal.server.graphqlServer.readinessProbe.timeoutSeconds | int | `1` |  |
| portal.server.graphqlServer.resources.limits.cpu | string | `"512m"` |  |
| portal.server.graphqlServer.resources.limits.ephemeral-storage | string | `"1Gi"` |  |
| portal.server.graphqlServer.resources.limits.memory | string | `"1Gi"` |  |
| portal.server.graphqlServer.resources.requests.cpu | string | `"125m"` |  |
| portal.server.graphqlServer.resources.requests.ephemeral-storage | string | `"500Mi"` |  |
| portal.server.graphqlServer.resources.requests.memory | string | `"350Mi"` |  |
| portal.server.licenseServer.containerPort | int | `8080` |  |
| portal.server.licenseServer.image.pullPolicy | string | `"Always"` |  |
| portal.server.licenseServer.image.repository | string | `"hce-license-module"` |  |
| portal.server.licenseServer.image.tag | string | `"master-ci"` |  |
| portal.server.licenseServer.resources.limits.cpu | string | `"250m"` |  |
| portal.server.licenseServer.resources.limits.ephemeral-storage | string | `"1Gi"` |  |
| portal.server.licenseServer.resources.limits.memory | string | `"512Mi"` |  |
| portal.server.licenseServer.resources.requests.cpu | string | `"25m"` |  |
| portal.server.licenseServer.resources.requests.ephemeral-storage | string | `"500Mi"` |  |
| portal.server.licenseServer.resources.requests.memory | string | `"300Mi"` |  |
| portal.server.licenseServer.service.port | int | `80` |  |
| portal.server.licenseServer.service.targetPort | int | `8080` |  |
| portal.server.licenseServer.service.type | string | `"ClusterIP"` |  |
| portal.server.nodeSelector | object | `{}` |  |
| portal.server.replicas | int | `1` |  |
| portal.server.serverVersionUpdater.image.pullPolicy | string | `"Always"` |  |
| portal.server.serverVersionUpdater.image.repository | string | `"mongo-utils"` |  |
| portal.server.serverVersionUpdater.image.tag | string | `"latest"` |  |
| portal.server.serverVersionUpdater.resources.limits.cpu | string | `"225m"` |  |
| portal.server.serverVersionUpdater.resources.limits.ephemeral-storage | string | `"200Mi"` |  |
| portal.server.serverVersionUpdater.resources.limits.memory | string | `"200Mi"` |  |
| portal.server.serverVersionUpdater.resources.requests.cpu | string | `"125m"` |  |
| portal.server.serverVersionUpdater.resources.requests.ephemeral-storage | string | `"100Mi"` |  |
| portal.server.serverVersionUpdater.resources.requests.memory | string | `"100Mi"` |  |
| portal.server.service.authServer.port | int | `9003` |  |
| portal.server.service.authServer.targetPort | int | `3000` |  |
| portal.server.service.graphqlServer.port | int | `9002` |  |
| portal.server.service.graphqlServer.targetPort | int | `8080` |  |
| portal.server.service.type | string | `"NodePort"` |  |
| portal.server.serviceAccountName | string | `"litmus-server-account"` |  |
| portal.server.tolerations | list | `[]` |  |
| portal.server.updateStrategy | object | `{}` |  |
| portal.server.waitForMongodb.image.pullPolicy | string | `"Always"` |  |
| portal.server.waitForMongodb.image.repository | string | `"curl"` |  |
| portal.server.waitForMongodb.image.tag | string | `"latest"` |  |
| portal.server.waitForMongodb.resources.limits.cpu | string | `"250m"` |  |
| portal.server.waitForMongodb.resources.limits.ephemeral-storage | string | `"200Mi"` |  |
| portal.server.waitForMongodb.resources.limits.memory | string | `"200Mi"` |  |
| portal.server.waitForMongodb.resources.requests.cpu | string | `"125m"` |  |
| portal.server.waitForMongodb.resources.requests.ephemeral-storage | string | `"100Mi"` |  |
| portal.server.waitForMongodb.resources.requests.memory | string | `"100Mi"` |  |
| portalScope | string | `"cluster"` |  |
| upgradeAgent.affinity | object | `{}` |  |
| upgradeAgent.controlPlane.image.pullPolicy | string | `"Always"` |  |
| upgradeAgent.controlPlane.image.repository | string | `"upgrade-agent-cp"` |  |
| upgradeAgent.controlPlane.image.tag | string | `"ci"` |  |
| upgradeAgent.nodeSelector | object | `{}` |  |
| upgradeAgent.tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.7.0](https://github.com/norwoodj/helm-docs/releases/v1.7.0)
