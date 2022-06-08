---
title: "Is Lambda Cloud Like AWS Cloud?"
linkTitle: "Is Lambda Cloud Like AWS Cloud?"
date: 2017-01-05
description: >
---

Hi,

Lambda Cloud is not really the same type of service as AWS Lambda (While AWS
Lambda is named that because it's like running functions rather than
persistent services, "Lambda Cloud" is named that because it's a part of
https://lambdalabs.com , a company started by functional programming
enthusiasts in 2012).

Most of our users are looking for instances to train ML models, which takes
days to weeks and isn't concerned with latency or boot times. Most of our
instances take a few minutes to boot, and we don't have a public API for
spinning up instances on demand.

You certainly can do inference in our cloud, but to be perfectly honest I
don't think it will be a good fit for you (currently).

I hope that answers your question, and please reach out if you have any
further questions.
