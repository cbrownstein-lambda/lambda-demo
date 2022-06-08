---
categories: ["Examples"]
tags: ["test", "sample", "docs"]
title: "Upload Data to Lambda Cloud"
linkTitle: "Upload Data to Lambda Cloud"
date: 2017-01-05
description: >
---

Hi,

There are multiple solutions for transferring your files to an instance. The
easiest is probably to use scp:
https://lambdalabs.com/blog/downloading-data-sets-lambda-cloud/

I personally like using rsync:

A good example command would be: rsync --archive --info=progress2
my_local_dir/ ubuntu@instance-ip:destination/ --archive tells rsync to copy
directories recursively and try to preserve permissions / modification times,
etc as much as possible. --info=progress2 tells rsync to show the overall
progress of the transfer as it goes.  "destination/" is relative to
/home/ubuntu/ on the instance, and for large transfers you probably want to
transfer into one of our cloud filesystems to avoid needing to rsync again for
future instances. If your filesystem is named "foobar" then if you attach it
to an instance it will be available at /home/ubuntu/foobar/. To copy into it
you could do: rsync --archive --info=progress2 my_local_dir/
ubuntu@instance-ip:foobar/

If you us a private key other than ~/.ssh/id_rsa when you ssh into your
instance, then you'll need to provide the path for that to rsync as well. You
can do that by adding -e "ssh -i /path/to/private/key". In the full command,
that would be:

rsync --archive --info=progress2 -e "ssh -i /path/to/private/key"
my_local_dir/ ubuntu@instance-ip:foobar/
