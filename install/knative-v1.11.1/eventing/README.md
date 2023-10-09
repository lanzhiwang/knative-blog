```yaml
customresourcedefinition.apiextensions.k8s.io
  apiserversources.sources.knative.dev
  brokers.eventing.knative.dev
  channels.messaging.knative.dev
  containersources.sources.knative.dev
  eventtypes.eventing.knative.dev
  parallels.flows.knative.dev
  pingsources.sources.knative.dev
  sequences.flows.knative.dev
  sinkbindings.sources.knative.dev
  subscriptions.messaging.knative.dev
  triggers.eventing.knative.dev

namespace
  knative-eventing

serviceaccount
  eventing-controller
  pingsource-mt-adapter
  eventing-webhook

clusterrolebinding.rbac.authorization.k8s.io
  eventing-controller
  eventing-controller-resolver
  eventing-controller-source-observer
  eventing-controller-sources-controller
  eventing-controller-manipulator
  knative-eventing-pingsource-mt-adapter
  eventing-webhook
  eventing-webhook-resolver
  eventing-webhook-podspecable-binding

rolebinding.rbac.authorization.k8s.io
  eventing-webhook

configmap
  config-br-default-channel
  config-br-defaults
  default-ch-webhook
  config-ping-defaults
  config-features
  config-kreference-mapping
  config-leader-election
  config-logging
  config-observability
  config-sugar
  config-tracing

deployment.apps
  eventing-controller
  pingsource-mt-adapter
  eventing-webhook

horizontalpodautoscaler.autoscaling
  eventing-webhook

poddisruptionbudget.policy
  eventing-webhook

service
  eventing-webhook

clusterrole.rbac.authorization.k8s.io
  addressable-resolver
  service-addressable-resolver
  serving-addressable-resolver
  channel-addressable-resolver
  broker-addressable-resolver
  flows-addressable-resolver
  eventing-broker-filter
  eventing-broker-ingress
  eventing-config-reader
  channelable-manipulator
  meta-channelable-manipulator
  knative-eventing-namespaced-admin
  knative-messaging-namespaced-admin
  knative-flows-namespaced-admin
  knative-sources-namespaced-admin
  knative-bindings-namespaced-admin
  knative-eventing-namespaced-edit
  knative-eventing-namespaced-view
  knative-eventing-controller
  knative-eventing-pingsource-mt-adapter
  podspecable-binding
  builtin-podspecable-binding
  source-observer
  eventing-sources-source-observer
  knative-eventing-sources-controller
  knative-eventing-webhook

role.rbac.authorization.k8s.io
  knative-eventing-webhook

validatingwebhookconfiguration.admissionregistration.k8s.io
  config.webhook.eventing.knative.dev
  validation.webhook.eventing.knative.dev

mutatingwebhookconfiguration.admissionregistration.k8s.io
  webhook.eventing.knative.dev
  sinkbindings.webhook.sources.knative.dev

secret
  eventing-webhook-certs

```

