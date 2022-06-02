---
title: Kubernetes
date: 2022-05-31 21:00:00 -500
categories: [kubernetes]
tags: [k8s]
---
## Install kubernetes control
Install kubectl
```shell
brew install kubectl
```
---
## Get version
```shell
kubectl version
```
---
## Remote into kubernetes pod
Get pod name:
```shell
kubectl get pods
```
Use kubectl exec:
```shell
kubectl exec --stdin --tty <pod name> -- /bin/bash
```
---
## Edit kube context
kubectl config unset takes a dot-delimited path. You can delete cluster/context/user entries by name. For example:
```shell
kubectl config unset users.<name>
kubectl config unset contexts.<context name>
kubectl config unset clusters.<clusters name>
```
---
## Manually Generate Job
Create job from existing cronjob:
```shell
kubectl create job --from=cronjob/[cronjob name] [job name]
```
Clean up:
```shell
kubectl delete job [job name]
```
---
## Logging
For convenience, looking across multiple pods of the same deployment use `stern`
```shell
brew install stern
```
```shell
stern <service name> --exclude "health|heartbeat"
```
---
Pod Management
```shell
kubectl get pod --field-selector=status.phase==Succeeded
```
```shell
kubectl delete pod --field-selector=status.phase==Succeeded
```
