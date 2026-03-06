---
title: "OpenShift imagestream error"
date: 2026-03-04
layout: post
---

When trying to deploy an application with an image where the openshift imagestream knows multiple images, you get this error message:


bash-5.1 ~ $ oc new-app nodejs:18~https://github.com/sclorg/nodejs-ex.git
warning: Cannot check if git requires authentication.
error: multiple images or templates matched "nodejs:18"

The argument "nodejs:18" could apply to the following container images, OpenShift image streams, or templates:

* Image stream "nodejs" (tag "20-ubi8-minimal") in project "openshift"
  Use --image-stream="openshift/nodejs:20-ubi8-minimal" to specify this image or template

* Image stream "nodejs" (tag "20-minimal-ubi9") in project "openshift"
  Use --image-stream="openshift/nodejs:20-minimal-ubi9" to specify this image or template

* Image stream "nodejs" (tag "18-minimal-ubi9") in project "openshift"
  Use --image-stream="openshift/nodejs:18-minimal-ubi9" to specify this image or template

* Image stream "nodejs" (tag "18-ubi8") in project "openshift"
  Use --image-stream="openshift/nodejs:18-ubi8" to specify this image or template

* Image stream "nodejs" (tag "18-ubi8-minimal") in project "openshift"
  Use --image-stream="openshift/nodejs:18-ubi8-minimal" to specify this image or template

To view a full list of matches, use 'oc new-app -S nodejs:18'





To get further you need to exactly specify which image you want like this:

oc new-app nodejs:18-ubi8~https://github.com/sclorg/nodejs-ex.git
