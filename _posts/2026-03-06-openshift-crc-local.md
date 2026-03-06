---
title: "CRC local Dev Cluster of RedHat OpenShift"
date: 2026-03-06
layout: post
---

# Red Hat OpenShift Local (formerly Red Hat CodeReady Containers)


Red Hat OpenShift has the option to install a local minimal cluster.
Maybe there ArgoCD will completely work with admin rights....

[https://developers.redhat.com/products/openshift-local](https://developers.redhat.com/products/openshift-local)

and then

[https://console.redhat.com/openshift/create/local](https://console.redhat.com/openshift/create/local)

to download the crc installer and your personal pull secret.


Then run crc setup, which takes a while for downlaoding 6.3GB: 

INFO Downloading bundle: /Users/peter/.crc/cache/crc_vfkit_4.21.0_arm64.crcbundle... 
4.29 GiB / 6.32 GiB [------------------------------------------------------>_________________________] 67.94% 1.42 MiB/s

After full setup run "crc start" and enter the pull-secret, after what the cluster goes live:

INFO Starting CRC VM for openshift 4.21.0...      
INFO CRC instance is running with IP 127.0.0.1    

The server is accessible via web console at: https://console-openshift-console.apps-crc.testing
