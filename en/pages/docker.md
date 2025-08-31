# Docker Snapshot Workflow

#### 1. Start & Attach Container
```bash
docker run -it --name test-container ubuntu:latest /bin/bash
```

#### 2. Modify container
```bash
apt update && apt install -y nginx
echo "Custom NGINX setup" > /etc/nginx/custom.txt
exit
```

#### 3. Commit Changes
```bash
docker commit test-container my-nginx-image:latest
```

#### 4. Run Image file w/o Entry Point
```bash
docker run -it my-nginx-image:latest /bin/bash

# With entry point
docker run --entrypoint start-nginx.sh my-nginx-image:latest
```

#### 5. Save/Publish Image file
```bash
docker save -o my-nginx-image.tar my-nginx-image:latest

# OR: Docker Hub
docker tag my-nginx-image:latest yourusername/my-nginx-image:latest
docker push yourusername/my-nginx-image:latest

# OR: GitHub Container Registry
docker tag my-nginx-image:latest ghcr.io/yourusername/my-nginx-image:latest
docker push ghcr.io/yourusername/my-nginx-image:latest
```

#### 6.2 OR: Load Image file as tar
```bash
docker load -i my-nginx-image.tar
```

#### 6.2 OR: Load Image file from hub
```bash
# OR: Docker Hub
docker pull yourusername/my-nginx-image:latest

# OR: GitHub Container Registry
docker pull ghcr.io/yourusername/my-nginx-image:latest
```

# Docker Cheatsheet
