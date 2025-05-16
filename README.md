# hadoop

Sure!
Here’s a **clean and clear step-by-step guide to install Hadoop 2.8.0 on Windows 10 (64-bit)**:

---

### ✅ **Step 1: Install Java JDK 1.8**

1. **Download Java JDK 1.8**
   Example: [Oracle JDK 8](https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html)

2. **Install Java in `C:\Java`**

3. **Verify installation:**
   Open Command Prompt and type:

   ```bash
   javac -version
   ```

   Should return something like:

   ```
   javac 1.8.0_xx
   ```

4. **Set Environment Variables:**

   * `JAVA_HOME` → `C:\Java`
   * Add `%JAVA_HOME%\bin` to `Path`

---

### ✅ **Step 2: Download and Extract Hadoop 2.8.0**

1. **Download Hadoop 2.8.0**
   Example: [Hadoop 2.8.0](https://archive.apache.org/dist/hadoop/core/hadoop-2.8.0/)
2. **Extract to `C:\Hadoop-2.8.0`**

---

### ✅ **Step 3: Set Environment Variables**

1. Add these to **System Environment Variables**:

   * `HADOOP_HOME` → `C:\Hadoop-2.8.0`
   * Add `%HADOOP_HOME%\bin` to `Path`
   * Confirm `JAVA_HOME` is correctly set from Step 1

---

### ✅ **Step 4: Configure Hadoop**

#### 1. **Configure `core-site.xml`**

* Path: `C:\Hadoop-2.8.0\etc\hadoop\core-site.xml`

```xml
<configuration>
  <property>
    <name>fs.defaultFS</name>
    <value>hdfs://localhost:9000</value>
  </property>
</configuration>
```

#### 2. **Configure `mapred-site.xml`**

* Rename: `mapred-site.xml.template` → `mapred-site.xml`
* Edit:

```xml
<configuration>
  <property>
    <name>mapreduce.framework.name</name>
    <value>yarn</value>
  </property>
</configuration>
```

#### 3. **Configure `hdfs-site.xml`**

* Path: `C:\Hadoop-2.8.0\etc\hadoop\hdfs-site.xml`

```xml
<configuration>
  <property>
    <name>dfs.replication</name>
    <value>1</value>
  </property>
  <property>
    <name>dfs.namenode.name.dir</name>
    <value>/hadoop-2.8.0/data/namenode</value>
  </property>
  <property>
    <name>dfs.datanode.data.dir</name>
    <value>/hadoop-2.8.0/data/datanode</value>
  </property>
</configuration>
```

#### 4. **Configure `yarn-site.xml`**

* Path: `C:\Hadoop-2.8.0\etc\hadoop\yarn-site.xml`

```xml
<configuration>
  <property>
    <name>yarn.nodemanager.aux-services</name>
    <value>mapreduce_shuffle</value>
  </property>
  <property>
    <name>yarn.nodemanager.auxservices.mapreduce.shuffle.class</name>
    <value>org.apache.hadoop.mapred.ShuffleHandler</value>
  </property>
</configuration>
```

#### 5. **Edit `hadoop-env.cmd`**

* Path: `C:\Hadoop-2.8.0\etc\hadoop\hadoop-env.cmd`
* Set JAVA\_HOME inside this file:

```cmd
set JAVA_HOME=C:\Java
```

---

### ✅ **Step 5: Create Required Directories**

* `C:\Hadoop-2.8.0\data`
* `C:\Hadoop-2.8.0\data\namenode`
* `C:\Hadoop-2.8.0\data\datanode`

---

### ✅ **Step 6: Replace `bin` Files (for Windows compatibility)**

1. Download pre-configured `bin` for Windows:

   * Example: [Hadoop 2.8.0 winutils](https://github.com/cdarlint/winutils)
2. Replace contents of:

   * `C:\Hadoop-2.8.0\bin` with downloaded files

---

### ✅ **Step 7: Format Hadoop NameNode**

1. Open Command Prompt as Administrator.
2. Run:

   ```bash
   hdfs namenode -format
   ```

---

### ✅ **Step 8: Start Hadoop Services**

1. Go to:

   ```bash
   cd C:\Hadoop-2.8.0\sbin
   ```
2. Start all services:

   ```bash
   start-all.cmd
   ```

---

### ✅ **Step 9: Verify Installation**

* Namenode UI: [http://localhost:50070](http://localhost:50070)
* YARN UI: [http://localhost:8088](http://localhost:8088)

---

### 🎉 **Congrats! Hadoop 2.8.0 is installed on Windows 10**

---

Would you also like me to give you a **single downloadable `.bat` file to automate all steps on Windows?**
If yes, just say "**Yes, script.**"


sudo apt update 
sudo apt install -y build-essential linux-headers-$(uname -г) 
