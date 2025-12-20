---
title: "OpenShift First Deployment"
date: 2025-12-20
layout: post
---

After a lot of trying I was able to deploy a deployment via redhat registry:

[peter@L]$ oc create deployment hello \
  --image=registry.access.redhat.com/ubi8/python-39
deployment.apps/hello created

[peter@L]$ oc patch deployment hello \
  --type='json' \
  -p='[
    {"op":"add","path":"/spec/template/spec/containers/0/command","value":["/bin/sh","-c"]},
    {"op":"add","path":"/spec/template/spec/containers/0/args","value":["echo Hello from OpenShift Sandbox > index.html && /usr/bin/python3 -m http.server 8080"]}
  ]'
deployment.apps/hello patched

[peter@L]$ oc expose deployment hello --port=8080
oc expose service hello
service/hello exposed
route.route.openshift.io/hello exposed

[peter@L]$ oc get route hello
NAME    HOST/PORT                                               PATH   SERVICES   PORT   TERMINATION   WILDCARD
hello   hello-pekastla-dev.apps.rm3.7wse.p1.openshiftapps.com          hello      8080                 None

[peter@L]$ oc get pod -l app=hello -n pekastla-dev
NAME                     READY   STATUS    RESTARTS   AGE
hello-554f47b468-2gv5x   1/1     Running   0          2m15s

[peter@LA]$ oc port-forward pod/hello-554f47b468-2gv5x 8080:8080 -n pekastla-dev
Forwarding from 127.0.0.1:8080 -> 8080
Forwarding from [::1]:8080 -> 8080
Handling connection for 8080
Handling connection for 8080

http://localhost:8080/ shows me: Hello from OpenShift Sandbox

Yeii
