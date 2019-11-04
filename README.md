# helm-prow-tekton

This repository contains the necessary helm charts to bootstrap a [prow](https://github.com/kubernetes/test-infra/tree/master/prow) + [tektoncd](https://github.com/tektoncd) stack in a kubernetes cluster.
This is the stack we use at [www.agriconomie.com](www.agriconomie.com) to build our ci/cd pipelines.

It also contains a step by step guide to setup andd configure the whole stack in such a way that the prow configuration and tekton pipelines are automatically kept in sync with a github repository.

## Prerequisites

To install the stack you will need the following

- A kubernetes cluster of any kind (EKS, kops, bare metal...)
- A github account
- helm and kubectl installed and configured

## How it works

1 - You create a github repository to manage the prow config files (config.yaml, plugins.yaml and job-config/*.yaml)
2 - You create a github repository to manage the tekton pipelines (tasks/*.yaml, pipelines/*.yaml)
3 - The stack deploys prow in the kubernetes cluster using helm
4 - The stack deploys tekton in the kubernetes cluster using helm
5 - You configure the `config-updater` plugin to keep the prow configuration in sync with the github repository created in 1
5 - You setup a tekton pipeline and a prow job to keep the tektons tasks and pipelines in sync with the github repository created in 2

All this is explained in the following section

## Step by step deployment and configuration guide

TODO
