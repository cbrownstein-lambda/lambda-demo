---
title: "What Can Lambda Cloud Be Used For?"
linkTitle: "What Can Lambda Cloud Be Used For?"
date: 2017-01-05
description: >
---

Hi,

Yes. Anything that your could run from a computer sitting under your desk with
the same specs as our instances (
https://lambdalabs.com/service/gpu-cloud/pricing ), you can run on our cloud
instances. (With the caveat that our instances are headless, so imagine that
you have a desktop under your desk that you can ssh into / use JupyterLab with
but no monitor).

Also, with the specifications of our instances, there are very few machine
learning workloads that cannot be run. (Generally ML workloads are limited by
Video RAM, and one 48 GiB VRAM A6000 is already a fairly large amount of
VRAM.)

Our instances start with Ubuntu 20.04 LTS + Lambda Stack, which gets you a lot
of the way toward running any ML workload, but you will often need to install
additional dependencies following the documentation provided from the
project.nvi

Where X is Google Colab or another machine learning cloud: Yes. All of our
instances come with a JupyterLabs WebIDE, and while Colab notebooks may need
some small tweaks to run on Lambda Cloud, I'm happy to help with that if
needed.


Where X involves inference or otherwise using a Lambda instances as part of
the back end of a customer facing website: Hi,

The short answer is yes, you can use our cloud for hosting. However, we
currently do not offer any guarantees around bandwidth and uptime. With that
said, our cloud is reliable and may be good enough depending on your specific
needs. We would need to do some due diligence and understand your
requirements. I'll have someone reach out to you to learn more and decide if
there is a mutual fit.
