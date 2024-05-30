# Module 9 AWS Services

## EC2

Create EC2 via AWS Console

### Docker on EC2

```bash
sudo yum updpate
```

```bash
sudo yum install docker
```

Start daemon

```bash
sudo service docker start
```

Confirm Docker process is running

```bash
ps aux | grep docker
```

Add ec2-user to docker group. Note, must login to refesh groups

```bash
sudo usermod -aG docker $USER
```

Test docker cmd

```bash
docker run hello-world
```

```bash
docker login
```

### Build and push the app

```bash
docker build -t tonyrudny/techdegree-module-9-node-app:1.0.0 .
```

```bash
docker push tonyrudny/techdegree-module-9-node-app:1.0.0
```

### Start the app on EC2

```bash
docker pull tonyrudny/techdegree-module-9-node-app:1.0.0
```

```bash
docker run -d -p 3000:3080 tonyrudny/techdegree-module-9-node-app:1.0.0
```

Open port `3000` in AWS Console for Security Group linked to the EC2!
