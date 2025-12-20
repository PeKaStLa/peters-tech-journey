---
title: "RedHat OpenShift"
date: 2025-12-19
layout: post
---


Red Hat OpenShift Sandbox and Red Hat OpenShift Container Platform (OCP)

Searching for OpenShift ressources and courses for the Sandbox I accidentally started my free 60-days OCP subscription.

Ihr Produkttest hat begonnen
Wir haben Ihnen die Download-Informationen auch per E-Mail zugesandt, damit Sie später darauf zurückgreifen können.
Sie haben noch 59 Tage, um Red Hat OpenShift Container Platform zu testen.

They gave me a small journey over the UI.
Pipelines, Storages, Helm, Workloads and... VMs:)

Just started a CentOS VM in OpenShift.


Now im trying to deploy anything to see if it works...


It's super difficult on the first try.

My oc/kubectl and helm in the CLI dont allow me a lot cause I dont have cluster access.

Also many repositories are not available (for now?) and the pods get into a CrashLoopBackOff when pulling images.

OpenShift internal images have weird ImageStreams where many images are behind one ImageStream. I dont know how to use them yet.

Then there are releases and new-apps which I dont know where to find...
