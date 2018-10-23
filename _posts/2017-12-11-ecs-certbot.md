---
layout: post
section-type: post
title: Issuing free certificates on ECS
category: tech
tags: [ 'aws', 'ecs', 'https' ]
---
I recently had to issue certificates for [EC2](https://aws.amazon.com/ec2/) machines that were created by
[ECS](https://aws.amazon.com/ecs/).
ECS is the elastic container service by AWS and EC2 is the VM infrastructure of AWS.
The go-to option of the Certificate Authority was [Let's Encrypt](https://letsencrypt.org/±) since it's supported
by the [EFF](https://www.eff.org/) organization and offers free certificates.
The process is automated by [certbot](https://github.com/certbot/certbot) and as you can imagine there are plenty of resources
on the web on how to use certbot on an EC2 instance. What I struggled to find was how to use certbot on the EC2 instances that
are created for ECS purposes.
The challenge with these instances is that they are not officially supported by the certbot and that they are by definition distributions with the bare minimum of dependencies running on them.
As a result you need to do some manual work for setting them up.
More specifically you need to clone the certbot since it's not available via yum and then you need to setup the web server by yourself, since the web server is running on the container and not the host instance.

First, you can use [this](https://gist.githubusercontent.com/le4ker/30323d994f3ef203949224e60a6bde57/raw/f2ac890960b08898369458e3652a29be665d7949/ecs-certbot.sh) script to install certbot and start the process of issuing the certificates:

<pre><code data-trim class="bash">
bash <(curl -s https://gist.githubusercontent.com/le4ker/30323d994f3ef203949224e60a6bde57/raw/f2ac890960b08898369458e3652a29be665d7949/ecs-certbot.sh)
</code></pre>

Then you will follow the instructions of certbot and after you finish your certificates will be placed under:

<pre><code data-trim class="bash">
/etc/letsencrypt/live/YOUR_DOMAIN/
</code></pre>

Now that you have the certificates, you have to set up the web server to use them.
Normally this is done by certbot, but using ECS means that you have an infrastructure that uses Docker containers, so your web server doesn't actually exist on the host instance.

Here is the configuration for [nginx](https://nginx.org/) that you need:

<script src="https://gist.github.com/le4ker/81ba102ee08b1943b58ac4dc2ba6bf40.js"></script>

This configuration scores an A on [ssllabs](https://www.ssllabs.com). I'll update the gist to score an A+ once I get the time to do it.

Last, don't forget to create the docker volumes in order to make available the certificates from your host to the containers that need them.

Keep encrypting!
