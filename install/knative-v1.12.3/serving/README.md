# serving

## 镜像列表

```
docker.io/istio/proxyv2:1.19.3
docker.io/istio/pilot:1.19.3
gcr.io/knative-releases/knative.dev/serving/cmd/activator@sha256:eff69d2271dde5f4ad0eb665d8a493773d7c78da05c2a5ef94c1d84dcac37cf1
gcr.io/knative-releases/knative.dev/serving/cmd/autoscaler@sha256:7908e2a3e2238d14044527f8f991cc76492e0de2110e2abef5e3ee4a59b43c4f
gcr.io/knative-releases/knative.dev/serving/cmd/autoscaler-hpa@sha256:f765925786e92f156c54ef8988893b230cadd155848781b53dc5d39f8cf55c5a
gcr.io/knative-releases/knative.dev/serving/cmd/controller@sha256:ea0f8f2ed5a603c42687ad397a4826bb720ea50ce39eef1b3a03927a920e4bc0
gcr.io/knative-releases/knative.dev/net-istio/cmd/controller@sha256:53b28cc099b7e2357513e9643c029b200eb6b8c7eb2279961c7e79b677a8a2b7
gcr.io/knative-releases/knative.dev/net-istio/cmd/webhook@sha256:90083eb29e6ab29a352fbf606257ca397e4039acb12f7c08152dc1e409e5ce50
gcr.io/knative-releases/knative.dev/serving/cmd/webhook@sha256:8883f4fff5c56ed512cc4a3a3ab178b7a3366e58ea2e6aee83d33bc6d287aa48

```

## 安装

```bash
$ kubectl apply -f https://github.com/knative/serving/releases/download/knative-v1.12.3/serving-crds.yaml

$ kubectl apply -f https://github.com/knative/serving/releases/download/knative-v1.12.3/serving-core.yaml

$ kubectl apply -l knative.dev/crd-install=true -f https://github.com/knative/net-istio/releases/download/knative-v1.12.1/istio.yaml

$ kubectl apply -f https://github.com/knative/net-istio/releases/download/knative-v1.12.1/istio.yaml

$ kubectl apply -f https://github.com/knative/net-istio/releases/download/knative-v1.12.1/net-istio.yaml

$ kubectl apply -f https://github.com/knative/serving/releases/download/knative-v1.12.3/serving-hpa.yaml

################################################################

# serving-crds.yaml

$ kubectl apply -f serving-crds.yml

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

################################################################

# serving-core.yaml

$ kubectl apply -f serving-core.yml

namespace/knative-serving

role.rbac.authorization.k8s.io/knative-serving-activator

clusterrole.rbac.authorization.k8s.io/knative-serving-activator-cluster
clusterrole.rbac.authorization.k8s.io/knative-serving-aggregated-addressable-resolver
clusterrole.rbac.authorization.k8s.io/knative-serving-addressable-resolver
clusterrole.rbac.authorization.k8s.io/knative-serving-namespaced-admin
clusterrole.rbac.authorization.k8s.io/knative-serving-namespaced-edit
clusterrole.rbac.authorization.k8s.io/knative-serving-namespaced-view
clusterrole.rbac.authorization.k8s.io/knative-serving-core
clusterrole.rbac.authorization.k8s.io/knative-serving-podspecable-binding
clusterrole.rbac.authorization.k8s.io/knative-serving-admin

serviceaccount/controller
serviceaccount/activator

clusterrolebinding.rbac.authorization.k8s.io/knative-serving-controller-admin
clusterrolebinding.rbac.authorization.k8s.io/knative-serving-controller-addressable-resolver
clusterrolebinding.rbac.authorization.k8s.io/knative-serving-activator-cluster

rolebinding.rbac.authorization.k8s.io/knative-serving-activator

secret/serving-certs-ctrl-ca
secret/knative-serving-certs
secret/routing-serving-certs
secret/webhook-certs

image.caching.internal.knative.dev/queue-proxy

configmap/config-autoscaler
configmap/config-defaults
configmap/config-deployment
configmap/config-domain
configmap/config-features
configmap/config-gc
configmap/config-leader-election
configmap/config-logging
configmap/config-network
configmap/config-observability
configmap/config-tracing

horizontalpodautoscaler.autoscaling/activator
horizontalpodautoscaler.autoscaling/webhook

poddisruptionbudget.policy/activator-pdb
poddisruptionbudget.policy/webhook-pdb

deployment.apps/activator
deployment.apps/autoscaler
deployment.apps/controller
deployment.apps/webhook

service/activator-service
service/autoscaler
service/controller
service/webhook

validatingwebhookconfiguration.admissionregistration.k8s.io/config.webhook.serving.knative.dev
validatingwebhookconfiguration.admissionregistration.k8s.io/validation.webhook.serving.knative.dev

mutatingwebhookconfiguration.admissionregistration.k8s.io/webhook.serving.knative.dev

################################################################

# istio.yaml

$ kubectl apply -l knative.dev/crd-install=true -f istio.yml
customresourcedefinition.apiextensions.k8s.io/authorizationpolicies.security.istio.io
customresourcedefinition.apiextensions.k8s.io/destinationrules.networking.istio.io
customresourcedefinition.apiextensions.k8s.io/envoyfilters.networking.istio.io
customresourcedefinition.apiextensions.k8s.io/gateways.networking.istio.io
customresourcedefinition.apiextensions.k8s.io/istiooperators.install.istio.io
customresourcedefinition.apiextensions.k8s.io/peerauthentications.security.istio.io
customresourcedefinition.apiextensions.k8s.io/proxyconfigs.networking.istio.io
customresourcedefinition.apiextensions.k8s.io/requestauthentications.security.istio.io
customresourcedefinition.apiextensions.k8s.io/serviceentries.networking.istio.io
customresourcedefinition.apiextensions.k8s.io/sidecars.networking.istio.io
customresourcedefinition.apiextensions.k8s.io/telemetries.telemetry.istio.io
customresourcedefinition.apiextensions.k8s.io/virtualservices.networking.istio.io
customresourcedefinition.apiextensions.k8s.io/wasmplugins.extensions.istio.io
customresourcedefinition.apiextensions.k8s.io/workloadentries.networking.istio.io
customresourcedefinition.apiextensions.k8s.io/workloadgroups.networking.istio.io

$ kubectl apply -f istio.yml

namespace/istio-system

serviceaccount/istio-ingressgateway-service-account
serviceaccount/istio-reader-service-account
serviceaccount/istiod

clusterrole.rbac.authorization.k8s.io/istio-reader-clusterrole-istio-system
clusterrole.rbac.authorization.k8s.io/istiod-clusterrole-istio-system
clusterrole.rbac.authorization.k8s.io/istiod-gateway-controller-istio-system

clusterrolebinding.rbac.authorization.k8s.io/istio-reader-clusterrole-istio-system
clusterrolebinding.rbac.authorization.k8s.io/istiod-clusterrole-istio-system
clusterrolebinding.rbac.authorization.k8s.io/istiod-gateway-controller-istio-system

role.rbac.authorization.k8s.io/istio-ingressgateway-sds
role.rbac.authorization.k8s.io/istiod

rolebinding.rbac.authorization.k8s.io/istio-ingressgateway-sds
rolebinding.rbac.authorization.k8s.io/istiod

configmap/istio
configmap/istio-sidecar-injector

deployment.apps/istio-ingressgateway
deployment.apps/istiod

service/istio-ingressgateway
service/istiod

horizontalpodautoscaler.autoscaling/istiod

poddisruptionbudget.policy/istio-ingressgateway
poddisruptionbudget.policy/istiod

mutatingwebhookconfiguration.admissionregistration.k8s.io/istio-sidecar-injector

validatingwebhookconfiguration.admissionregistration.k8s.io/istio-validator-istio-system

################################################################

# net-istio.yaml
$ kubectl apply -f net-istio.yml

clusterrole.rbac.authorization.k8s.io/knative-serving-istio

gateway.networking.istio.io/knative-ingress-gateway
gateway.networking.istio.io/knative-local-gateway

service/knative-local-gateway
service/net-istio-webhook

configmap/config-istio

peerauthentication.security.istio.io/webhook
peerauthentication.security.istio.io/net-istio-webhook

deployment.apps/net-istio-controller
deployment.apps/net-istio-webhook

secret/net-istio-webhook-certs
secret/routing-serving-certs

mutatingwebhookconfiguration.admissionregistration.k8s.io/webhook.istio.networking.internal.knative.dev

validatingwebhookconfiguration.admissionregistration.k8s.io/config.webhook.istio.networking.internal.knative.dev

################################################################

# serving-hpa.yaml

$ kubectl apply -f serving-hpa.yml

deployment.apps/autoscaler-hpa

service/autoscaler-hpa

```


