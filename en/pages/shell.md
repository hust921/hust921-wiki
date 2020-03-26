# Shell

## SSH-Key login
**Generate key**
<pre><code class="bash">ssh-keygen -t rsa -b 4096 -C "<email>"
</code></pre>

**Start ssh-agent**
<pre><code class="bash">eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa
</code></pre>

Now place `id_rsa.pub` on the server.


**Identify**
<pre><code class="bash">ssh-add ~/.ssh/mykey
</code></pre>

**Run at startup**
To automatically use key, setup `ssh-agent` to run in bashrc/zshrc/etc.

And modify your ssh config `~/.ssh/config`. Able to add multiple users (Host) to the same domain.
<pre><code class="bash">
Host MyGithub
    HostName github.com
    User hust921
    IdentityFile ~/.ssh/id_rsa
</code></pre>

## Git
### Git flow
![git flow commands overview](../images/git-flow-commands.png)

## OpenSSL
...

## Nmap
...

## CURL
...

## dd
...

## netcat
...
