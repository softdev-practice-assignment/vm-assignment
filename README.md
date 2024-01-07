# Assignment - VM

## VM 1 (Master)

### 1. create vm linux-ubuntu-64

### 2. install java

```bash
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
```

### 3. install jenkins

```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

### 4. run jenkins

```bash
jenkins
```

#### if Jenkins fails to start because a port is in use run

```bash
systemctl edit jenkins
```

#### add this one (or maybe the another port.)

```
[Service]
Environment="JENKINS_PORT=8081"
```

Ref: [install jenkins on Linux](https://www.jenkins.io/doc/book/installing/linux/)
