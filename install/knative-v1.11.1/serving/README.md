
```yaml
customresourcedefinition.apiextensions.k8s.io
  certificates.networking.internal.knative.dev
  configurations.serving.knative.dev
  clusterdomainclaims.networking.internal.knative.dev
  domainmappings.serving.knative.dev
  ingresses.networking.internal.knative.dev
  metrics.autoscaling.internal.knative.dev
  podautoscalers.autoscaling.internal.knative.dev
  revisions.serving.knative.dev
  routes.serving.knative.dev
  serverlessservices.networking.internal.knative.dev
  services.serving.knative.dev
  images.caching.internal.knative.dev

namespace
  knative-serving

role.rbac.authorization.k8s.io
  knative-serving-activator

clusterrole.rbac.authorization.k8s.io
  knative-serving-activator-cluster
  knative-serving-aggregated-addressable-resolver
  knative-serving-addressable-resolver
  knative-serving-namespaced-admin
  knative-serving-namespaced-edit
  knative-serving-namespaced-view
  knative-serving-core
  knative-serving-podspecable-binding
  knative-serving-admin

clusterrolebinding.rbac.authorization.k8s.io
  knative-serving-controller-admin
  knative-serving-controller-addressable-resolver
  knative-serving-activator-cluster

serviceaccount
  controller
  activator

rolebinding.rbac.authorization.k8s.io
  knative-serving-activator

secret
  serving-certs-ctrl-ca
  knative-serving-certs
  control-serving-certs
  routing-serving-certs
  webhook-certs

image.caching.internal.knative.dev
  queue-proxy

configmap
  config-autoscaler
  config-defaults
  config-deployment
  config-domain
  config-features
  config-gc
  config-leader-election
  config-logging
  config-network
  config-observability
  config-tracing

horizontalpodautoscaler.autoscaling
  activator
  webhook

poddisruptionbudget.policy
  activator-pdb
  webhook-pdb

deployment.apps
  activator
  autoscaler
  controller
  webhook

service
  activator-service
  autoscaler
  controller
  webhook

validatingwebhookconfiguration.admissionregistration.k8s.io
  config.webhook.serving.knative.dev
  validation.webhook.serving.knative.dev

mutatingwebhookconfiguration.admissionregistration.k8s.io
  webhook.serving.knative.dev

```



