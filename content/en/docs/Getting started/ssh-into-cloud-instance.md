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

## Using SSH in Windows

### Generate a SSH public-private key pair

1. Download and install the
   [latest version of PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).
   PuTTY is a widely used SSH client for Windows.

   {{% alert title="Note" color="info" %}}
   Be sure to download the **MSI ('Windows Installer') 64-bit x86**
   installer package.
   {{% /alert %}}

1. Open the newly installed **PuTTYgen** application.

1. In the **Actions** section, click **Generate** to generate a public/private
   key pair.

1. Click **Save private key** and save your SSH private key to a file.

### Add your SSH public key to Lambda Cloud

1. Log into your Lambda Cloud account.

   In the left sidebar of the Lambda Cloud dashboard, click **SSH Keys**.

1. Click **Add SSH key**.

1. In **PuTTYgen**, copy to the clipboard the text that appears under the
   label **Public key for pasting into OpenSSH authorized_keys file**. This
   text is your SSH public key.

1. Paste your SSH public key into the box that says _Paste your public key
   here_.

   In the box that says _Title_, give your public key a name. For example, you
   can use your name or the name of your computer.

1. Click **Add SSH key**.

1. Launch a Lambda Cloud instance. Under the **Which SSH key should it use?**
   dropdown menu, select the SSH key you added.

### Connect to your Lambda Cloud instance

1. In the Lambda Cloud instances dashboard, find the IP address for the
   instance you created.

1. Open the **PuTTY** application.

1. In the **PuTTY** sidebar, under **Connection > SSH**, select **Auth**. In
   the **Authentication parameters** section, click **Browse...** and choose
   the SSH private key you created.

1. In the **PuTTY** sidebar, select **Session**.

   In the box labeled **Host Name (or IP address)**, enter the IP address of
   your instance.

   Click **Open**.

1. When presented with the **PuTTY Security Alert** dialog, click **Accept**.

1. Login as `ubuntu`.

You should now be connected to your instance using SSH.
