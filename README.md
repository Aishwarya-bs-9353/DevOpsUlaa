# Java Web Application Deployment on Apache Tomcat

## Overview
This document describes the step-by-step procedure followed to deploy a Java web application (WAR file) on Apache Tomcat using Maven and Git.

---

## 1. System Update and Java Installation
```bash
apt update
apt install openjdk-17-jre-headless -y
```
- Updated system packages
- Installed OpenJDK 17 required for Tomcat

---

## 2. Apache Tomcat Installation
```bash
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.115/bin/apache-tomcat-9.0.115.tar.gz
tar -zxvf apache-tomcat-9.0.115.tar.gz
rm -rf apache-tomcat-9.0.115.tar.gz
```

---

## 3. Tomcat Configuration
```bash
vi apache-tomcat-9.0.115/conf/tomcat-users.xml
vi apache-tomcat-9.0.115/webapps/manager/META-INF/context.xml
```
- Configured users and roles
- Enabled access to Tomcat Manager

---

## 4. Start Tomcat
```bash
sh apache-tomcat-9.0.115/bin/startup.sh
```

---

## 5. Clone Application Source Code
```bash
git clone https://github.com/Aishwarya-bs-9353/DevOpsUlaa.git
```

---

## 6. Maven Installation and Verification
```bash
bash <(curl -sL https://tinyurl.com/52ykfnu5)
source .bashrc
mvn --version
```

---

## 7. Build the Application
```bash
cd DevOpsUlaa/ulaa/
mvn clean package
```
- Generated WAR file in target directory

---

## 8. Deploy WAR to Tomcat
```bash
sh apache-tomcat-9.0.115/bin/shutdown.sh
cp DevOpsUlaa/ulaa/target/ulaa.war apache-tomcat-9.0.115/webapps/
sh apache-tomcat-9.0.115/bin/startup.sh
```

---

## 9. Verification
- WAR file deployed successfully
- Application accessible at:
```
http://<SERVER-IP>:8080/ulaa
```

---

## Conclusion
The Java web application was successfully built using Maven and deployed on Apache Tomcat.
