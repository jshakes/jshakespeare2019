---
date: 2015-08-09 22:46:00+05:00
layout: post
permalink: giving-clients-jailed-sftp-access
title: Giving clients 'jailed' SFTP access to their sites
---

Here’s a common problem amongst freelance web developers. You’ve built a client a website and are dutifully hosting it on your low-end Linux VPS (you know, the one you munged into a web-server by copy-pasting several hundred commands you don’t understand from Stack Overflow answers and Ubuntu forums).

But what happens when that client sends you an email asking for access to those files so their prodigal 9 year old niece can make some tweaks to the site in exchange for a pack of gum, instead of the hundreds of dollars you would charge?

Setting up an FTP server is complex and can lead to vulnerabilities if you don’t know what you’re doing. And obviously you don’t want them poking around on the command line with their own system login that you _think_ you gave the right permissions to.

One good solution is to give the client what’s called a ‘jailed’ account login. And furthermore, disable them from using that account to SSH in on the command line, and instead force them to use SFTP.

Before we begin, I’m going to assume you’re using OpenSSH as your SSH client (you probably are). Also it needs to be at least version 4.9.1 (it probably is). Also most, if not all the following commands will need to be run as root.

First off, create a group called `sftp`. This will contain all users we want to give SFTP access to.

`groupadd sftp`

Now, we tell OpenSSH that it can let anyone in the `sftp` group access their own home directories via SFTP. Open `/etc/ssh/sshd_config` and at the _end of the file_ paste this, which will let users SFTP into their own home directories (that’s what the `%h` is for):

```bash
Subsystem sftp internal-sftp
Match Group sftp
  ChrootDirectory %h
  ForceCommand internal-sftp
  AllowTcpForwarding no
```

And reload the SSH config

`/etc/init.d/ssh reload`

Next, add the user you want to grant SFTP access, whose name is Steve. We’ll add Steve straight into the `sftp` group

`useradd -g sftp steve`.

Steve also needs a password and he needs a home directory

`passwd steve` and `mkdir /home/steve`

Now we run the following

`usermod -s /bin/false steve`

to deny Steve ever getting shell access

`chown root:root /home/steve` and `chmod 0755 /home/steve`

so Steve can upload and download files to his home directory

Steve can now SFTP into his own little jail cell and do whatever he wants in there without breaking anything. However this isn’t much use, because his website files are located elsewhere on the server, let’s say in `/var/www/stevestevington.com/html`. 

The solution is to mount the website directory into Steve’s home directory. That way any changes he makes will be reflected on the actual website. First make the directory to mount

`mkdir /home/steve/html`

Then mount the website files on it

`mount --bind /var/www/stevestevington.com/html /home/steve/html`

And finally, ensure that Steve has permission to modify those files. The easiest way to do this is with `chown`, but you may need to ensure the group ownership remains with whatever group your webserver belongs to, eg `web` 

`chown steve:web /var/www/stevestevington.com/html `

Et voila. Send Steve his login, a link to download Cyberduck, and let him play around with his site to his heart’s content and not bother you ever again.
