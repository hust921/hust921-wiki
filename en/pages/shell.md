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
### Git Server (no deps)
[Git init --bare](https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server)

### Git flow
![git flow commands overview](../images/git-flow-commands.png)

## Docker & docker-compose
### Docker
**List Running Containers**
<pre><code class="bash">docker ps
docker ps -a # Shows prev runs too
</code></pre>

**List Docker Volumes**
<pre><code class="bash">docker volume ls
docker volume inspect &lt;optional-container-name&gt;
</code></pre>

**List Installed Images**
<pre><code class="bash">docker image ls
</code></pre>

**See (live) logs (shell output) from running container**
<pre><code class="bash">docker logs --follow &lt;container-name&gt;
</code></pre>

**Open shell in RUNNING container**
<pre><code class="bash">docker exec -it &lt;container-name&gt; bash
</code></pre>

**Create container from image and run command**
*This will not make changes to the image. But the container created can be found using* `docker ps -a` *and committed to new image with* `docker commit`.
<pre><code class="bash">docker run &lt;image_id&gt; &lt;myCommand&gt;
# example (using image tag)
docker run -t mytag ping www.example.com
</code></pre>

**Commit changes made to container and save a new image**
<pre><code class="bash">docker ps -a 
docker commit &lt;container_id&gt; &lt;new_image_name&gt;:&lt;tag_name(optional)&gt;
</code></pre>

**Dockerfile build argument (ARG myArg=defaultValue)**
<pre><code class="bash">docker build -t &lt;dockerfile&gt; --build-arg myArg=otherValue .
</code></pre>

### docker-compose
[docker-compose](https://docs.docker.com/compose/) Compose is a tool for defining and running multi-container Docker applications.

**Build or rebuild service**
<pre><code class="bash">docker-compose build --pull
</code></pre>

**Run <cmd> in container, (--rm) remove container after <cmd> is done**
<pre><code class="bash">docker-compose run --rm &lt;container-name&gt; &lt;cmd&gt;
</code></pre>

**Create and start containers**
<pre><code class="bash">docker-compose up -d &lt;option: --remove-orphans&gt;
</code></pre>

## OpenSSL
- To encode a file text.plain you can use: `openssl enc -base64 -in text.plain -out text.base64`
- To decode a file the the decrypt option (-d) has to be used: `openssl enc -d -base64 -in text.base64 -out text.plain`

## Nmap
- Ping Scan `nmap -sP 10.0.0.0/24`
- OS Detection `nmap -O`
- Resolve Hostnames `nmap -sL`
- Try TCP Connection `nmap -sT`
- Fast (common 100 ports) `nmap -T4 -F`
- Aggressive `nmap -A`
- Service Versions (eg: OPENSSH 4.3) `nmap -Sv`
- TCP ACK & SYN `nmap -PS`
- Stealth Scan `nmap -sS`

## CURL
- Write to file `-o <file>`
- HTTP Method `-X POST`
- Data `-d '{"var": "value"} ..'`
- Data file `-d @file`
- User Agent `-A 'gecko etc..'`
- Header `-H "SoapAction: MyMethod"`
- Ignore SSL `-k` or `--insecure`
- Auth (basic) `-u user:pass`

## netcat
- Connect to server `nc <host> <port>`
- Listen on port `nc -l 0.0.0.0 8080`
- Execute shell `nc -l 0.0.0.0 8080 -e /bin/bash`
- Transmit file: `nc [host] [port] < filename.in` Receive file: `nc [host] [port] > filename.out`
- Continue after client disconnect `nc -k -l ..`

## rsync
...

## dd
...
