## `README.md` (krishna-js45) --hosted by rajkrishna

### STEP 1 — Enable WSL (Windows PowerShell – Admin)

```powershell
wsl --install
```

**After this, you should see:**
System asks for restart or confirms WSL installed.

---

### STEP 2 — Install Ubuntu

```powershell
wsl --list --online
wsl --install -d Ubuntu-20.04
```

**After this, you should see:**
Ubuntu downloading → Ubuntu terminal opens.

---

### STEP 3 — Create Linux User (Ubuntu Terminal)

```text
Enter new UNIX username:
New password:
Retype new password:
```

**After this, you should see:**

```text
username@DESKTOP-XXXX:~$
```

---

### STEP 4 — Update Ubuntu

```bash
sudo apt update
sudo apt upgrade -y
```

**After this, you should see:**
Command finishes without errors and returns to prompt.

---

### STEP 5 — Install Java (Required)

```bash
sudo apt install openjdk-11-jdk -y
```

**After this, you should see:**
Java installation completes successfully.

---

### STEP 6 — Verify Java

```bash
java -version
```

**After this, you should see:**

```text
openjdk version "11"
```

---

### STEP 7 — Install SSH

```bash
sudo apt install openssh-server openssh-client -y
```

**After this, you should see:**
SSH packages installed successfully.

---

### STEP 8 — Enable Passwordless SSH

```bash
ssh localhost
```

Type `yes` when asked and enter your Linux password.

```bash
exit
```

**After this, you should see:**
Login to localhost succeeds without error.

---

### STEP 9 — Download Hadoop

```bash
wget https://archive.apache.org/dist/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz
```

**After this, you should see:**
File downloaded to home directory.


"If the hadoop didnt install go down"
---

### STEP 10 — Extract Hadoop

```bash
tar -xvzf hadoop-3.3.6.tar.gz
```

**After this, you should see:**
`hadoop-3.3.6` folder created.

---

### STEP 11 — Configure Environment Variables

```bash
nano ~/.bashrc
```

Add at the end:

```bash
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export HADOOP_HOME=$HOME/hadoop-3.3.6
export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
```

Apply changes:

```bash
source ~/.bashrc
```

**After this, you should see:**
No errors after `source`.

---

### STEP 12 — Format HDFS (One Time Only)

```bash
hdfs namenode -format
```

**After this, you should see:**

```text
Storage directory has been successfully formatted
```

---

### STEP 13 — Start Hadoop

```bash
start-dfs.sh
start-yarn.sh
```

**After this, you should see:**
NameNode, DataNode, ResourceManager started.

---

### STEP 14 — Verify in Browser

Open in browser:

```text
http://localhost:9870
http://localhost:8088
```

**After this, you should see:**
HDFS and YARN web dashboards.

---

### STEP 15 — Test HDFS

```bash
hdfs dfs -mkdir /test
hdfs dfs -ls /
```

**After this, you should see:**

```text
drwxr-xr-x   - username supergroup /test
```

---

### Restart (Next Day / After Shutdown)

```bash
start-dfs.sh
start-yarn.sh
```

---

This format is **lab-perfect**, **copy-safe**, and **exam-friendly**.
If you want, next I can:

* Compress this to **one-page lab manual**
* Add **common errors + fixes**
* Convert this into a **printable PDF**


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

So we stop fighting the network

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

AFTER COMPLETE THIS CONTINUE WITH ```STEP 10
