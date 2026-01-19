## `README.md` (COMMAND-ONLY)

You can paste **this entire content** into `README.md`.

````md
# Hadoop Installation – Windows 10 (WSL)

---

## STEP 1 — Enable WSL (Windows PowerShell – Admin)

```powershell
wsl --install
````

# Restart system if prompted

---

## STEP 2 — Install Ubuntu 20.04

```powershell
wsl --list --online
wsl --install -d Ubuntu-20.04
```

# Create Linux username and password

---

## STEP 3 — Update Ubuntu

```bash
sudo apt update
sudo apt upgrade -y
```

---

## STEP 4 — Install Java (Required)

```bash
sudo apt install openjdk-11-jdk -y
```

---

## STEP 5 — Verify Java

```bash
java -version
```

---

## STEP 6 — Install SSH

```bash
sudo apt install openssh-server openssh-client -y
```

---

## STEP 7 — Enable Passwordless SSH

```bash
ssh-keygen -t rsa -P ""
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
ssh localhost
exit
```

---

## STEP 8 — Download Hadoop

```bash
wget https://archive.apache.org/dist/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz
```
if its not work go down...
---

## STEP 9 — Extract Hadoop

```bash
tar -xvzf hadoop-3.3.6.tar.gz
```

---

## STEP 10 — Set Environment Variables

```bash
nano ~/.bashrc
```

```bash
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export HADOOP_HOME=$HOME/hadoop-3.3.6
export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
```

```bash
source ~/.bashrc
```

---

## STEP 11 — Configure Hadoop Files

```bash
nano ~/hadoop-3.3.6/etc/hadoop/core-site.xml
```

```xml
<configuration>
 <property>
  <name>fs.defaultFS</name>
  <value>hdfs://localhost:9000</value>
 </property>
</configuration>
```

```bash
nano ~/hadoop-3.3.6/etc/hadoop/hdfs-site.xml
```

```xml
<configuration>
 <property>
  <name>dfs.replication</name>
  <value>1</value>
 </property>
</configuration>
```

---

## STEP 12 — Create HDFS Directories

```bash
mkdir -p ~/hadoopdata/namenode
mkdir -p ~/hadoopdata/datanode
```

---

## STEP 13 — Format NameNode

```bash
hdfs namenode -format
```

---

## STEP 14 — Start Hadoop

```bash
start-dfs.sh
start-yarn.sh
```

---

## STEP 15 — Verify Hadoop

```bash
jps
```

---

## STEP 16 — Hadoop Web UI

```text
HDFS  : http://localhost:9870
YARN  : http://localhost:8088
```

---

## STEP 17 — Test HDFS

```bash
hdfs dfs -mkdir /test
hdfs dfs -ls /
```

---

## STOP HADOOP

```bash
stop-yarn.sh
stop-dfs.sh
```

```
```
```
```

---
---
---
---
---

HADOOP WEB INSTALL

👉 **Your network blocks Apache mirrors.**
This is extremely common in college / hostel / lab networks.

So we stop fighting the network and use the **correct engineering workaround**.

---


### STEP 1 — Download in Windows (Browser)

Open **Chrome / Edge** in Windows and download:

**File:** `hadoop-3.3.6.tar.gz`
**URL:**
[https://archive.apache.org/dist/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz](https://archive.apache.org/dist/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz)

Wait until the download **fully completes**.

---

### STEP 2 — Move file into Ubuntu (ONLY ONE COMMAND)

```bash
mv /mnt/c/Users/hari/Downloads/hadoop-3.3.6.tar.gz ~/
```

> If your Windows username is different, replace `hari`.

---

### STEP 3 — Verify (ONLY THIS)

```bash
ls
```

You **must** see:

```text
hadoop-3.3.6.tar.gz
```

---


