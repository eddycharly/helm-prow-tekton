tekton
======


Current chart version is `0.8.0`

Source code can be found [here](https://github.com/eddycharly/helm-prow-tekton/helm/tekton)



## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.artifactBucket | string | `nil` |  |
| config.artifactPvc | string | `nil` |  |
| config.defaults._example | string | `"################################\n#                              #\n#    EXAMPLE CONFIGURATION     #\n#                              #\n################################\n\n# This block is not actually functional configuration,\n# but serves to illustrate the available configuration\n# options and document them in a way that is accessible\n# to users that `kubectl edit` this config map.\n#\n# These sample configuration options may be copied out of\n# this example block and unindented to be in the data block\n# to actually change the configuration.\n\n# default-timeout-minutes contains the default number of\n# minutes to use for TaskRun and PipelineRun, if none is specified.\ndefault-timeout-minutes: \"60\"  # 60 minutes\n\n# default-service-account contains the default service account name\n# to use for TaskRun and PipelineRun, if none is specified.\ndefault-service-account: \"default\"\n"` |  |
| config.logging."loglevel.controller" | string | `"info"` |  |
| config.logging."loglevel.webhook" | string | `"info"` |  |
| config.logging.zap-logger-config | string | `"{\n  \"level\": \"info\",\n  \"development\": false,\n  \"sampling\": {\n    \"initial\": 100,\n    \"thereafter\": 100\n  },\n  \"outputPaths\": [\"stdout\"],\n  \"errorOutputPaths\": [\"stderr\"],\n  \"encoding\": \"json\",\n  \"encoderConfig\": {\n    \"timeKey\": \"\",\n    \"levelKey\": \"level\",\n    \"nameKey\": \"logger\",\n    \"callerKey\": \"caller\",\n    \"messageKey\": \"msg\",\n    \"stacktraceKey\": \"stacktrace\",\n    \"lineEnding\": \"\",\n    \"levelEncoder\": \"\",\n    \"timeEncoder\": \"\",\n    \"durationEncoder\": \"\",\n    \"callerEncoder\": \"\"\n  }\n}\n"` |  |
| config.observability._example | string | `"################################\n#                              #\n#    EXAMPLE CONFIGURATION     #\n#                              #\n################################\n\n# This block is not actually functional configuration,\n# but serves to illustrate the available configuration\n# options and document them in a way that is accessible\n# to users that `kubectl edit` this config map.\n#\n# These sample configuration options may be copied out of\n# this example block and unindented to be in the data block\n# to actually change the configuration.\n\n# metrics.backend-destination field specifies the system metrics destination.\n# It supports either prometheus (the default) or stackdriver.\n# Note: Using Stackdriver will incur additional charges.\nmetrics.backend-destination: prometheus\n\n# metrics.stackdriver-project-id field specifies the Stackdriver project ID. This\n# field is optional. When running on GCE, application default credentials will be\n# used and metrics will be sent to the cluster's project if this field is\n# not provided.\nmetrics.stackdriver-project-id: \"\u003cyour stackdriver project id\u003e\"\n\n# metrics.allow-stackdriver-custom-metrics indicates whether it is allowed\n# to send metrics to Stackdriver using \"global\" resource type and custom\n# metric type. Setting this flag to \"true\" could cause extra Stackdriver\n# charge.  If metrics.backend-destination is not Stackdriver, this is\n# ignored.\nmetrics.allow-stackdriver-custom-metrics: \"false\"\n"` |  |
| deploy.dashboard.knativeService | bool | `false` |  |
| deploy.dashboard.pipelines | bool | `false` |  |
| deploy.dashboard.tasks | bool | `false` |  |
| images.dashboard.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/dashboard/cmd/dashboard@sha256"` |  |
| images.dashboard.tag | string | `"b985769636204f2d736e20dbafa27ff68ba07c218445925da094a2dd8ab07a6a"` |  |
| images.dashboardWebhook.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/experimental/webhooks-extension/cmd/extension@sha256"` |  |
| images.dashboardWebhook.tag | string | `"db812c6ef08e84870b3ed294b00ac5bdabbc67efca177786d6f307150674f2a2"` |  |
| images.pipeline.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/controller@sha256"` |  |
| images.pipeline.tag | string | `"72a2bda21b5bc23550e94fdf7cee8a6e5bd82601f5d81a6237fc2b8c42321a59"` |  |
| images.pipelineWebhook.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/webhook@sha256"` |  |
| images.pipelineWebhook.tag | string | `"1d6336f2748cb8e5c19b17191a54c6adbbc77e2d1c60818f93282ec482bb2957"` |  |
| ingress | object | `{}` |  |
| nodeSelector.dashboard | object | `{}` |  |
| nodeSelector.dashboardWebhook | object | `{}` |  |
| nodeSelector.pipeline | object | `{}` |  |
| nodeSelector.pipelineWebhook | object | `{}` |  |
| pipelineUtils.bash-noop-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/bash@sha256"` |  |
| pipelineUtils.bash-noop-image.tag | string | `"a96b5840cdeb2a6598a8566a8607b925732286a8fdf15147be3591b7c7fb41f7"` |  |
| pipelineUtils.build-gcs-fetcher-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/vendor/github.com/googlecloudplatform/cloud-builders/gcs-fetcher/cmd/gcs-fetcher@sha256"` |  |
| pipelineUtils.build-gcs-fetcher-image.tag | string | `"5be2e14ed6b986198beca21a93af34e807586dcf9155babeca7f5971a2fa0311"` |  |
| pipelineUtils.creds-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/creds-init@sha256"` |  |
| pipelineUtils.creds-image.tag | string | `"8f8c43a115984e90db3b0cb3fcd46e1699ec15515ca7d258571a44c7d76040ca"` |  |
| pipelineUtils.entrypoint-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/entrypoint@sha256"` |  |
| pipelineUtils.entrypoint-image.tag | string | `"5c2a7261d923b8af29ad3be34a9c9a3abd1ed11a030ca1cc207293d203755ab4"` |  |
| pipelineUtils.git-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/git-init@sha256"` |  |
| pipelineUtils.git-image.tag | string | `"00466e8ec7d8a289140893523d33261ba5006dfb1bd9b96aee2736fc739dba5a"` |  |
| pipelineUtils.gsutil-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/gsutil@sha256"` |  |
| pipelineUtils.gsutil-image.tag | string | `"0130ec562b897c5929123d4e14cd3271cd58102f1f411f52cb6f415088bf5944"` |  |
| pipelineUtils.imagedigest-exporter-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/imagedigestexporter@sha256"` |  |
| pipelineUtils.imagedigest-exporter-image.tag | string | `"23e2de68c86de494aba98dabf02b175efc051827c52350bdd9a89f6a3d969ea9"` |  |
| pipelineUtils.kubeconfig-writer-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/kubeconfigwriter@sha256"` |  |
| pipelineUtils.kubeconfig-writer-image.tag | string | `"912d30334e63899f3875806b0633b5ddf3470d64fbd2333fc2c534afcfa9872d"` |  |
| pipelineUtils.nop-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/nop@sha256"` |  |
| pipelineUtils.nop-image.tag | string | `"b77955ba2711e1ba30ab48670bcafd725ddc01a105d173256e158053914dc42c"` |  |
| pipelineUtils.pr-image.repository | string | `"gcr.io/tekton-releases/github.com/tektoncd/pipeline/cmd/pullrequest-init@sha256"` |  |
| pipelineUtils.pr-image.tag | string | `"26a181a89c00ab840599508e905d1cfeed5db2b4ea41fbcc63c22979389e4a46"` |  |
| replicas.dashboard | int | `1` |  |
| replicas.dashboardWebhook | int | `1` |  |
| replicas.pipeline | int | `1` |  |
| replicas.pipelineWebhook | int | `1` |  |
