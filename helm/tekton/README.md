tekton
======


Current chart version is `0.8.0`

Source code can be found [here](https://github.com/eddycharly/helm-prow-tekton/helm/tekton)



## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.artifactBucket | object | `{}` |  |
| config.artifactPvc | object | `{}` |  |
| config.defaults | object | `{}` |  |
| config.logging."loglevel.controller" | string | `"info"` |  |
| config.logging."loglevel.webhook" | string | `"info"` |  |
| config.logging.zap-logger-config | string | `"{\n  \"level\": \"info\",\n  \"development\": false,\n  \"sampling\": {\n    \"initial\": 100,\n    \"thereafter\": 100\n  },\n  \"outputPaths\": [\"stdout\"],\n  \"errorOutputPaths\": [\"stderr\"],\n  \"encoding\": \"json\",\n  \"encoderConfig\": {\n    \"timeKey\": \"\",\n    \"levelKey\": \"level\",\n    \"nameKey\": \"logger\",\n    \"callerKey\": \"caller\",\n    \"messageKey\": \"msg\",\n    \"stacktraceKey\": \"stacktrace\",\n    \"lineEnding\": \"\",\n    \"levelEncoder\": \"\",\n    \"timeEncoder\": \"\",\n    \"durationEncoder\": \"\",\n    \"callerEncoder\": \"\"\n  }\n}\n"` |  |
| config.observability | object | `{}` |  |
| dashboard.enabled | bool | `true` | Enable dashboard |
| dashboard.image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/dashboard/cmd/dashboard@sha256"` | Dashboard docker image tag |
| dashboard.image.tag | string | `"b985769636204f2d736e20dbafa27ff68ba07c218445925da094a2dd8ab07a6a"` |  |
| dashboard.ingress.annotations | object | `{}` | Dashboard ingress annotations |
| dashboard.ingress.enabled | bool | `false` | Enable dashboard ingress |
| dashboard.ingress.host | string | `"example.com"` | (string) Dashboard ingress host name |
| dashboard.nodeSelector | object | `{}` | Dashboard node selector |
| dashboard.replicas | int | `1` | Dashboard replicas |
| dashboardWebhook.enabled | bool | `true` | Enable dashboard webhook |
| dashboardWebhook.image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/experimental/webhooks-extension/cmd/extension@sha256"` | Dashboard webhook docker image tag |
| dashboardWebhook.image.tag | string | `"db812c6ef08e84870b3ed294b00ac5bdabbc67efca177786d6f307150674f2a2"` |  |
| dashboardWebhook.nodeSelector | object | `{}` | Dashboard webhook node selector |
| dashboardWebhook.replicas | int | `1` | Dashboard webhook replicas |
| pipeline.helpers.bash-noop-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/bash@sha256"` |  |
| pipeline.helpers.bash-noop-image.tag | string | `"a96b5840cdeb2a6598a8566a8607b925732286a8fdf15147be3591b7c7fb41f7"` |  |
| pipeline.helpers.build-gcs-fetcher-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/vendor/github.com/googlecloudplatform/cloud-builders/gcs-fetcher/cmd/gcs-fetcher@sha256"` |  |
| pipeline.helpers.build-gcs-fetcher-image.tag | string | `"5be2e14ed6b986198beca21a93af34e807586dcf9155babeca7f5971a2fa0311"` |  |
| pipeline.helpers.creds-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/creds-init@sha256"` |  |
| pipeline.helpers.creds-image.tag | string | `"8f8c43a115984e90db3b0cb3fcd46e1699ec15515ca7d258571a44c7d76040ca"` |  |
| pipeline.helpers.entrypoint-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/entrypoint@sha256"` |  |
| pipeline.helpers.entrypoint-image.tag | string | `"5c2a7261d923b8af29ad3be34a9c9a3abd1ed11a030ca1cc207293d203755ab4"` |  |
| pipeline.helpers.git-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/git-init@sha256"` |  |
| pipeline.helpers.git-image.tag | string | `"00466e8ec7d8a289140893523d33261ba5006dfb1bd9b96aee2736fc739dba5a"` |  |
| pipeline.helpers.gsutil-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/gsutil@sha256"` |  |
| pipeline.helpers.gsutil-image.tag | string | `"0130ec562b897c5929123d4e14cd3271cd58102f1f411f52cb6f415088bf5944"` |  |
| pipeline.helpers.imagedigest-exporter-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/imagedigestexporter@sha256"` |  |
| pipeline.helpers.imagedigest-exporter-image.tag | string | `"23e2de68c86de494aba98dabf02b175efc051827c52350bdd9a89f6a3d969ea9"` |  |
| pipeline.helpers.kubeconfig-writer-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/kubeconfigwriter@sha256"` |  |
| pipeline.helpers.kubeconfig-writer-image.tag | string | `"912d30334e63899f3875806b0633b5ddf3470d64fbd2333fc2c534afcfa9872d"` |  |
| pipeline.helpers.nop-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/nop@sha256"` |  |
| pipeline.helpers.nop-image.tag | string | `"b77955ba2711e1ba30ab48670bcafd725ddc01a105d173256e158053914dc42c"` |  |
| pipeline.helpers.pr-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/pullrequest-init@sha256"` |  |
| pipeline.helpers.pr-image.tag | string | `"26a181a89c00ab840599508e905d1cfeed5db2b4ea41fbcc63c22979389e4a46"` |  |
| pipeline.image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/controller@sha256"` | Pipeline controller docker image tag |
| pipeline.image.tag | string | `"72a2bda21b5bc23550e94fdf7cee8a6e5bd82601f5d81a6237fc2b8c42321a59"` |  |
| pipeline.nodeSelector | object | `{}` | Pipeline controller node selector |
| pipeline.replicas | int | `1` | Pipeline controller replicas |
| pipelineWebhook.enabled | bool | `true` | Enable pipeline webhook |
| pipelineWebhook.image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/webhook@sha256"` | Pipeline webhook docker image tag |
| pipelineWebhook.image.tag | string | `"1d6336f2748cb8e5c19b17191a54c6adbbc77e2d1c60818f93282ec482bb2957"` |  |
| pipelineWebhook.nodeSelector | object | `{}` | Pipeline webhook node selector |
| pipelineWebhook.replicas | int | `1` | Pipeline webhook replicas |
