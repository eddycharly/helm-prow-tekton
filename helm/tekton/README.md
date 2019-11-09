

tekton
======

## Description

This chart bootstraps installation of [tekton pipeline](https://github.com/tektoncd/pipeline).

It optionnaly can install the following tekton additionnal components :
  - tekton pipeline webhook
  - tekton dashboard (see [here](https://github.com/tektoncd/dashboard))
  - tekton dashboard webhook extensions


## Installation

`helm upgrade --install my-tekton --namespace tekton ./tekton`

This will install tekton pipelines and tekton dashboard in the tekton namespace.

You can override default values, see [Chart Values](#chart-values) section.

## Version

Current chart version is `0.8.0`

## Source

Source code can be found [here](https://github.com/eddycharly/helm-prow-tekton/helm/tekton)



## Chart Values


| Key | Type | Description | Default |
|-----|------|-------------|---------|
| dashboard.enabled | bool | Enable dashboard | `true` |
| dashboard.image.repository | string | Dashboard docker image repository | `"gcr.io/tekton-releases/github.com/tektoncd/dashboard/cmd/dashboard@sha256"` |
| dashboard.image.tag | string | Dashboard docker image tag | `"b985769636204f2d736e20dbafa27ff68ba07c218445925da094a2dd8ab07a6a"` |
| dashboard.ingress.annotations | object | Dashboard ingress annotations | `{}` |
| dashboard.ingress.enabled | bool | Enable dashboard ingress | `false` |
| dashboard.ingress.host | string | Dashboard ingress host name | `"example.com"` |
| dashboard.nodeSelector | object | Dashboard node selector | `{}` |
| dashboard.replicas | int | Dashboard replicas | `1` |
| dashboardWebhook.enabled | bool | Enable dashboard webhook | `true` |
| dashboardWebhook.image.repository | string | Dashboard webhook docker image repository | `"gcr.io/tekton-releases/github.com/tektoncd/experimental/webhooks-extension/cmd/extension@sha256"` |
| dashboardWebhook.image.tag | string | Dashboard webhook docker image tag | `"db812c6ef08e84870b3ed294b00ac5bdabbc67efca177786d6f307150674f2a2"` |
| dashboardWebhook.nodeSelector | object | Dashboard webhook node selector | `{}` |
| dashboardWebhook.replicas | int | Dashboard webhook replicas | `1` |
| pipeline.config.artifactBucket | object | Pipeline configuration for artifact bucket (see https://github.com/tektoncd/pipeline/blob/master/docs/install.md) | `{}` |
| pipeline.config.artifactPvc | object | Pipeline configuration for artifact pvc (see https://github.com/tektoncd/pipeline/blob/master/docs/install.md) | `{}` |
| pipeline.config.defaults | object | Pipeline configuration for default values (see https://github.com/tektoncd/pipeline/blob/master/docs/install.md) | `{}` |
| pipeline.config.logging | object | Pipeline configuration for logging (see https://github.com/tektoncd/pipeline/blob/master/docs/install.md) | `{"loglevel.controller":"info","loglevel.webhook":"info","zap-logger-config":"{\n  \"level\": \"info\",\n  \"development\": false,\n  \"sampling\": {\n    \"initial\": 100,\n    \"thereafter\": 100\n  },\n  \"outputPaths\": [\"stdout\"],\n  \"errorOutputPaths\": [\"stderr\"],\n  \"encoding\": \"json\",\n  \"encoderConfig\": {\n    \"timeKey\": \"\",\n    \"levelKey\": \"level\",\n    \"nameKey\": \"logger\",\n    \"callerKey\": \"caller\",\n    \"messageKey\": \"msg\",\n    \"stacktraceKey\": \"stacktrace\",\n    \"lineEnding\": \"\",\n    \"levelEncoder\": \"\",\n    \"timeEncoder\": \"\",\n    \"durationEncoder\": \"\",\n    \"callerEncoder\": \"\"\n  }\n}\n"}` |
| pipeline.config.observability | object | Pipeline configuration for observability (see https://github.com/tektoncd/pipeline/blob/master/docs/install.md) | `{}` |
| pipeline.helperImages.bash-noop-image.repository | string | Pipeline controller bash-noop-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/bash@sha256"` |
| pipeline.helperImages.bash-noop-image.tag | string | Pipeline controller bash-noop-image helper image tag | `"a96b5840cdeb2a6598a8566a8607b925732286a8fdf15147be3591b7c7fb41f7"` |
| pipeline.helperImages.build-gcs-fetcher-image.repository | string | Pipeline controller build-gcs-fetcher-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/vendor/github.com/googlecloudplatform/cloud-builders/gcs-fetcher/cmd/gcs-fetcher@sha256"` |
| pipeline.helperImages.build-gcs-fetcher-image.tag | string | Pipeline controller build-gcs-fetcher-image helper image tag | `"5be2e14ed6b986198beca21a93af34e807586dcf9155babeca7f5971a2fa0311"` |
| pipeline.helperImages.creds-image.repository | string | Pipeline controller creds-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/creds-init@sha256"` |
| pipeline.helperImages.creds-image.tag | string | Pipeline controller creds-image helper image tag | `"8f8c43a115984e90db3b0cb3fcd46e1699ec15515ca7d258571a44c7d76040ca"` |
| pipeline.helperImages.entrypoint-image.repository | string | Pipeline controller entrypoint-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/entrypoint@sha256"` |
| pipeline.helperImages.entrypoint-image.tag | string | Pipeline controller entrypoint-image helper image tag | `"5c2a7261d923b8af29ad3be34a9c9a3abd1ed11a030ca1cc207293d203755ab4"` |
| pipeline.helperImages.git-image.repository | string | Pipeline controller git-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/git-init@sha256"` |
| pipeline.helperImages.git-image.tag | string | Pipeline controller git-image helper image tag | `"00466e8ec7d8a289140893523d33261ba5006dfb1bd9b96aee2736fc739dba5a"` |
| pipeline.helperImages.gsutil-image.repository | string | Pipeline controller gsutil-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/gsutil@sha256"` |
| pipeline.helperImages.gsutil-image.tag | string | Pipeline controller gsutil-image helper image tag | `"0130ec562b897c5929123d4e14cd3271cd58102f1f411f52cb6f415088bf5944"` |
| pipeline.helperImages.imagedigest-exporter-image.repository | string | Pipeline controller imagedigest-exporter-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/imagedigestexporter@sha256"` |
| pipeline.helperImages.imagedigest-exporter-image.tag | string | Pipeline controller imagedigest-exporter-image helper image tag | `"23e2de68c86de494aba98dabf02b175efc051827c52350bdd9a89f6a3d969ea9"` |
| pipeline.helperImages.kubeconfig-writer-image.repository | string | Pipeline controller kubeconfig-writer-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/kubeconfigwriter@sha256"` |
| pipeline.helperImages.kubeconfig-writer-image.tag | string | Pipeline controller kubeconfig-writer-image helper image tag | `"912d30334e63899f3875806b0633b5ddf3470d64fbd2333fc2c534afcfa9872d"` |
| pipeline.helperImages.nop-image.repository | string | Pipeline controller nop-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/nop@sha256"` |
| pipeline.helperImages.nop-image.tag | string | Pipeline controller nop-image helper image tag | `"b77955ba2711e1ba30ab48670bcafd725ddc01a105d173256e158053914dc42c"` |
| pipeline.helperImages.pr-image.repository | string | Pipeline controller pr-image helper image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/pullrequest-init@sha256"` |
| pipeline.helperImages.pr-image.tag | string | Pipeline controller pr-image helper image tag | `"26a181a89c00ab840599508e905d1cfeed5db2b4ea41fbcc63c22979389e4a46"` |
| pipeline.image.repository | string | Pipeline controller docker image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/controller@sha256"` |
| pipeline.image.tag | string | Pipeline controller docker image tag | `"72a2bda21b5bc23550e94fdf7cee8a6e5bd82601f5d81a6237fc2b8c42321a59"` |
| pipeline.nodeSelector | object | Pipeline controller node selector | `{}` |
| pipeline.replicas | int | Pipeline controller replicas | `1` |
| pipelineWebhook.enabled | bool | Enable pipeline webhook | `true` |
| pipelineWebhook.image.repository | string | Pipeline webhook docker image repository | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/webhook@sha256"` |
| pipelineWebhook.image.tag | string | Pipeline webhook docker image tag | `"1d6336f2748cb8e5c19b17191a54c6adbbc77e2d1c60818f93282ec482bb2957"` |
| pipelineWebhook.nodeSelector | object | Pipeline webhook node selector | `{}` |
| pipelineWebhook.replicas | int | Pipeline webhook replicas | `1` |


Specify each parameter using the --set key=value[,key=value] argument to helm install.
