---
layout: post
title: "4 Ways to Install Plex (one is unexpected)"
date: 2020-05-23 09:00:00 -0500
categories: self-hosted
tags: homelab rancher kubernetes portainer docker plex self-hosted
image:
  path: /assets/img/headers/movie-theater.webp
---

I'm a huge fan of virtualization and containerization (if you couldn't tell already)!  Today, we'll walk though the various ways to install Plex step-by-step.  We also see how easy it is to get Plex running on Docker and Kubernetes using Rancher.

{% include embed/youtube.html id='MG_1XQxWns0' %}

📺 [Watch Video](https://www.youtube.com/watch?v=MG_1XQxWns0)

## Id for Container

Get Id and Group Id

```bash
id yourusername
```

Should see something like this:

```bash
uid=1001(technotim) gid=1001(technotim) groups=1001(technotim),27(sudo),999(docker)
```

## Mount Shares During Boot

Install `cifs-utils`

```bash
sudo apt-get install cifs-utils
```

Create credentials files for share

```bash
sudo nano /home/technotim/.smbcredentials
```

Set permissions

```bash
chmod 600 ~/.smbcredentials
```

```bash
username=yourUsyourusernameername  
password=yourPassword
```

Edit `/etc/fstab`

```bash
//192.168.0.22/plex_media/movies /mnt/movies cifs credentials=/home/technotim/.smbcredentials 0 0
//192.168.0.22/plex_media/music /mnt/music cifs credentials=/home/technotim/.smbcredentials 0 0
```

Then reboot or

```bash
sudo mount -a
```

to mount

## Links

⚙️ See all the hardware I recommend at <https://l.technotim.live/gear>

🚀 Don't forget to check out the [🚀Launchpad repo](https://l.technotim.live/quick-start) with all of the quick start source files
