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

### 5. login to jenkins

![https://cdn.discordapp.com/attachments/941704517597163572/1193515645665542194/image.png?ex=65acff10&is=659a8a10&hm=c0242641fbab0c6550456530091cbe01699eeca1f2729aae77ed9dff04f9a2b7&](jenkins login page)

#### เช็ค ip address ของ vm ผ่าน _ifconfig_ จากนั้นเข้า browser แล้วเข้า _{vm-address}:{port}_

#### ถ้ามีให้ใส่รหัส ให้ใช้คำสั่ง _cat /var/lib/jenkins/secrets/initialAdminPassword_ ในลง vm

```yaml
default user
username: admin
password: เอามาจาก cat /var/lib/jenkins/secrets/initialAdminPassword
```
