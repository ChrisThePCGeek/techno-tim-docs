---
layout: post
title: "Automated NUT Server Install"
date: 2022-11-28 09:00:00 -0500
categories: homelab
tags: homelab nut self-hosted ups pdu open-source automation
image:
  path: /assets/img/headers/nut-script.webp
---

Here's a quick way to automate your battery backups and UPSes with and open source service called NUT server and a raspberry Pi.  

{% include embed/youtube.html id='HgKeD4320c0' %}
📺 [Watch Video](https://www.youtube.com/watch?v=HgKeD4320c0)

## NUT Server Install script

Be sure to check out (and star) the repo with an automated NUT server install!

⭐ <https://github.com/dzomaya/NUTandRpi>

## Instructions

Be sure you have a raspberry pi or any machine running Debian / Ubuntu Linux.  Then plug in your UPS via USB and then SSH into your Pi.

Then download th script.

```bash
wget https://raw.githubusercontent.com/dzomaya/NUTandRpi/main/scripts/nutinstall.sh
```

Make the script executable.

```bash
sudo chmod +x nutinstall.sh
```

Run the script.

```bash
sudo ./nutinstall.sh
```

Answer a few questions.

Be sure to keep your SNMP community string safe and treat this like a password.

You can now access NUT in a browser by going to:

<http://yourRasberryPiIPaddress/cgi-bin/nut/upsstats.cgi>

You can also query your device using SNMP

```bash
snmpwalk -v2c -c yourSNMPv2cCommunity yourRasberryPiIPaddress .1.3.6.1.4.1.8072.1.3.2.4.1.2
```

## Advanced

To see advanced configuration and configuring NUT Server and NUT client, see my [Network UPS Tools (NUT) Ultimate Guide](/posts/NUT-server-guide/).

## Join the conversation

<blockquote class="twitter-tweet" data-dnt="true" data-theme="dark"><p lang="en" dir="ltr">I figured I’d share my quick <a href="https://twitter.com/hashtag/homelab?src=hash&amp;ref_src=twsrc%5Etfw">#homelab</a> video on the open source NUT Server here too! <a href="https://t.co/e7wA0fNGk4">pic.twitter.com/e7wA0fNGk4</a></p>&mdash; Techno Tim (@TechnoTimLive) <a href="https://twitter.com/TechnoTimLive/status/1597442260886769664?ref_src=twsrc%5Etfw">November 29, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Links

⚙️ See all the hardware I recommend at <https://l.technotim.live/gear>

🚀 Don't forget to check out the [🚀Launchpad repo](https://l.technotim.live/quick-start) with all of the quick start source files
