---
categories: ["Examples"]
tags: ["test", "sample", "docs"]
title: "Access Lambda Cloud instance using SSH"
linkTitle: "Access Lambda Cloud instance using SSH"
date: 2022-06-09
description: >
---

## Using SSH in Linux and macOS

### Generate a SSH public-private key pair

If you do not already have a SSH public-private key pair, you will need to
generate one in order to access your Lambda Cloud instance using SSH.

1. In a terminal, run the following command and follow the prompts given to
   you:

       ssh-keygen

   This command generates a SSH public-private key pair. By default, the
   public key is stored in the file `~/.ssh/id_rsa.pub`, and the private key
   is stored in the file `~/.ssh/id_rsa`.

   {{% alert title="Warning" color="warning" %}}
   Do not share the SSH private key. Anyone with the SSH private key and the
   key passphrase will be able to access your Lambda Cloud instance.
   {{% /alert %}}

### Add your SSH public key to Lambda Cloud

1. Run the following in the terminal to output your SSH public key:

       cat ~/.ssh/id_rsa.pub

   Alternatively, you can open `~/.ssh/id_rsa.pub` using a text editor.

1. Copy the SSH public key to your clipboard.

1. Log into your Lambda Cloud account.

   In the left sidebar of the Lambda Cloud dashboard, click **SSH Keys**.

1. Click **Add SSH key**.

1. Paste your SSH public key into the box that says _Paste your public key
   here_.

   In the box that says _Title_, give your public key a name. For example, you
   can use your name or the name of your computer.

1. Click **Add SSH key**.

1. Launch a Lambda Cloud instance. Under the **Which SSH key should it use?**
   dropdown menu, select the SSH key you added.

### Connect to your Lambda Cloud instance

In the instances dashboard, find the **SSH Login** command for the instance
you created. Run that command in a terminal.

You should now be connected to your instance using SSH.
