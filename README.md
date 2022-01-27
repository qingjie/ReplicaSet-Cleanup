# ReplicaSet-Cleanup
revisionHistoryLimit

```
$ diff nginx-deployment-extensions.yaml nginx-deployment-app.yaml
1c1
< apiVersion: extensions/v1beta1
---
> apiVersion: apps/v1beta1
```

```
$ kubectl apply -f nginx-deployment-extensions.yaml
deployment "nginx" created
$ kubectl get deployment nginx -o yaml | grep revisionHistoryLimit
$
```

```
$ kubectl apply -f nginx-deployment-apps.yaml
deployment "nginx" configured
$ kubectl get deployment nginx -o yaml | grep revisionHistoryLimit
revisionHistoryLimit: 2
```
---
Ref: https://blog.heptio.com/replicaset-cleanup-defaults-heptioprotip-9c3750981991
