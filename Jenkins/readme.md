Here are **neat, well-structured, and interview-ready notes on Jenkins** (clear, simple, and complete):

---

# 🚀 **JENKINS – COMPLETE NOTES**

---

## 🔹 **What is Jenkins?**

* **Jenkins** is an **open-source automation tool**.
* Used for **CI/CD (Continuous Integration & Continuous Deployment)**.
* Helps automate:

  * Build
  * Test
  * Deploy applications

👉 Written in **Java** and runs on **port 8080** by default.

---

## 🔹 **Why Jenkins?**

* Automates repetitive tasks
* Faster delivery of software
* Reduces human errors
* Easy integration with DevOps tools

---

## 🔹 **CI/CD Concept**

### 🔸 Continuous Integration (CI)

* Developers push code frequently to Git
* Jenkins builds & tests automatically

### 🔸 Continuous Deployment (CD)

* After build & test → application deployed automatically

---

## 🔹 **Jenkins Architecture**

![Image](https://images.openai.com/static-rsc-4/vKHwthCltzk3-GXlwmjFSp75ahJtsm1TDQ-qyTdQd5J5bCw0Ckq7D0hws4gl7DJYO0DzijUp4KxxS-4ZQRXTVbtHm_JqLl5VF5Q4ybTsvFq10nSxjYEa2-o4-qXOUqYFbweWPAZ71hy8k9I_wm15ytfpCEW8W6wvfZwX0Lv3m5UQrRwxO3sZXuXWYLT6ZvlQ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/TAmDxcYqo7OQI0uVrBCqDDC47GmQoYAhaqe4SQpYD4G6wqW0kbvdloWrcprTx0KM21LppGGkcEk3Tvewpk3j72h1uyEq0N-Jwi6VT5_lctKcGbo7Y16tT_HrX_X8x8A2F6vtGSjZYUxjz8AYlovRqYVoU_2FStn0UE-kK-LtTvk28GtvfGQA_w4F_fybjZ4Q?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/W10GEPUpZJ6oayQwX2-rIT7uTFmUsPe2uUWd2SL29H6CmjuXXyBsFl13XCTSn4UzPPbKCSLHbL_HdiJ3UNcIhVkko5f1HrG_NRuvrJ0K4pW1wfZ_c7CgRN6lwi8Z9fJznpA55ftbkoM2xSOePNSN4gLHYxhmg9GqGB5A3AFfRvWv616BJvRmlOE3YLa8PVk_?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/LWsQiqAMYrSJygNvdBcTwaDKp3G0tI0ibE7e0SIQ1HBi0E9feyQLFSErCBlCt8BDJG-VTb8XsFdR4qGU8Uf2suPODQXB2QU7qeWmwScCL4J0vEYtkJhmDPQveI4VZUGlSSFyvd54l03EbS6H50Du7ABMQ1MowV-7r1ree7jminqkSa9-6iwZ7KejGV8UsHf5?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/P5HHk-eOKTyQKvKLo6RMMwqYStvnVWWo-CJbif7YN2qDlvUupGeFaBlnRR1ggfx7fwyylzSpf1YjenKmQTvjZJo4mVLKYCiMJNNzFOQULAutqU68l6SUgnKkW_vUujJn7DTPcV9OSlIIfsgQlT3-xRR95YWEz_T4Cw_09a1RgDlKmCCrQX9GaThtv2xZPSKI?purpose=fullsize)

### Components:

1. **Master (Controller)**

   * Manages jobs
   * Schedules builds
   * Controls agents

2. **Agent (Slave)**

   * Executes jobs
   * Can be multiple nodes

3. **Executor**

   * Executes build tasks inside agent

---

## 🔹 **Types of Jenkins Jobs**

1. **Freestyle Project**

   * Simple job
   * UI-based configuration

2. **Pipeline Job**

   * Defined using **Jenkinsfile**
   * Code-based automation

3. **Multibranch Pipeline**

   * Automatically builds branches from Git

---

## 🔹 **Jenkins Installation (Linux – Amazon Linux / Ubuntu)**

### Install Java

```bash
sudo yum install java-17-amazon-corretto -y
```

### Add Jenkins Repo

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo \
https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

### Install Jenkins

```bash
sudo yum install jenkins -y
```

### Start Jenkins

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

### Access Jenkins

```
http://<server-ip>:8080
```

---

## 🔹 **Initial Setup**

* Unlock Jenkins:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

* Install suggested plugins
* Create admin user

---

## 🔹 **Important Jenkins Plugins**

* Git Plugin
* Maven Plugin
* Docker Plugin
* Pipeline Plugin
* Blue Ocean Plugin

---

## 🔹 **Jenkins Pipeline**

## Types:

### 1. Declarative Pipeline

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
    }
}
```

### 2. Scripted Pipeline

```groovy
node {
    stage('Build') {
        echo 'Building...'
    }
}
```

---

## 🔹 **Jenkinsfile**

* File that defines pipeline
* Stored in Git repository

👉 Example:

```groovy
pipeline {
    agent any

    stages {
        stage('Code Checkout') {
            steps {
                git 'https://github.com/example/repo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
```

---

## 🔹 **Build Triggers**

* Poll SCM
* GitHub Webhook
* Build periodically
* Manual trigger

---

## 🔹 **Jenkins with Git**

* Connect using Git URL
* Use credentials (SSH/HTTPS)
* Automatically triggers builds on code changes

---

## 🔹 **Jenkins with Docker**

* Build Docker image
* Push to DockerHub
* Deploy container

👉 Example:

```groovy
stage('Docker Build') {
    steps {
        sh 'docker build -t myapp .'
    }
}
```

---

## 🔹 **Jenkins with Maven**

```bash
mvn clean install
```

* Used for Java builds

---

## 🔹 **Jenkins Environment Variables**

* `BUILD_ID`
* `BUILD_NUMBER`
* `JOB_NAME`
* `WORKSPACE`

---

## 🔹 **Jenkins Security**

* Role-based access
* Credentials management
* Enable authentication

---

## 🔹 **Backup & Restore**

* Backup:

```bash
/var/lib/jenkins
```

* Restore by copying data back

---

## 🔹 **Common Jenkins Commands**

```bash
systemctl start jenkins
systemctl stop jenkins
systemctl restart jenkins
systemctl status jenkins
```

---

## 🔹 **Common Issues**

* Port 8080 blocked
* Java not installed
* Permission issues
* Disk space full

---

## 🔹 **Advantages**

* Open source
* Large plugin ecosystem
* Easy integration
* Strong community support

---

## 🔹 **Disadvantages**

* UI is outdated
* Plugin dependency issues
* Maintenance required

---

## 🔹 **Real-Time CI/CD Flow**

![Image](https://images.openai.com/static-rsc-4/AXITSfeF6aTPzcNaFcmvnU7iSTl8wMBOEwg1kyALgyPmFuXR-zbGllEShdoakr46hTnRCTEZLYRhIg7Ntq4XTgzoZZc9mXg5OoI_1NMS3cblZck-nwjpczZwxzXvhK86oJmn5ODmYmh5mvBUzUSH6udMuGh4v57-pblmdb750zUSRrhjO9Rg1A3buntkWvp5?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/zFshwszBD1rY-N3g5nO-7jsyCGm0td0vyCECMSi4Uz2EK9CNPdrdzMEdimUDJZ3Pp21zymF0ImBH1x4kVYEI0xj_2leW9P7WCJO5DAgdCdWZGjShn6m4CzCTzwpfQ90CYzI7hEe0seNsLShsqo2pp2lz4jmCdzOxSV5w0XwiFTwfvG729k1obOp7PKfufRrb?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/cOJqOEg2KlQiekueYpcjd9gJWAb44HKQ2-m1WALGdfQXC51m0wVZ-AREifY1pZN_zdcQG9kKCb-rumGHAx4NEw8TPkS6jd00FSKK4q8QXTWAPGmMyjJAd18w2wsU4ZlR6WNJkn1_jSsjAd-o6n9VJSj92cmM7yiuWvHIRpBdH4E6NhBEUbY3bKa3s-O-jRBK?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/hwwMEauz-4DE_vw4P_7XOsAm2Etph6bT-V5SOjJ3k_xIrbLWghu7kmHjZOWMVy1NKuAvY2-J5IAHxi-OSDFXqAx5WkSOBLlQj7SsO87og4U4yl-rBORWcAaLbpUuy96zQNeljKOwsB1ZmJWqcUGQPScASjWxd-FwoLGBgFtuTyIgPe6usZ4w4ru6zqRSlNZu?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Ky85_R33-9Q235W_FQQexfZZ0l8ICHLOYtfqiW4C-Yr941c16fl9FPcPt1l_XX-3TvpEIn0qwcfZbokNJrK-2YuWeup4JfXMyb5nEeeqEeEZa4lDiby8SOFVa2ycUhBZW8Lxy2tSi3nXR92cawyouLCcCNlWD3v8qCyA0Y8sOGawXG8zIkKiDQWt5ZAW1716?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/-1FH7krDKKG1TXPy08-hqHD6turtZ6FozcqXu9pxQE2WOdDBA5BrNFfx-JmsCy5g5spkVCyrVBPeM4UzJ_ygMq0g08P7WvUqjq7ibgfOSZ_2FG4mJ2ZwCfWUzMsIe2JR7pLBWW7gV68W1CN5Se2zwhpRI9ZNKaYxy5iOzDWjxDwavRtxRaM9tLPC_LqBf4Es?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/SXGv2z-f2jf3AzamqW5pjmN4f1pNI3KamgR-Wayfipb2i6jh30ZnBqvfhqRqjJiSXEUQ6FA9CKp5lnTA-Gy-znN6neZkwFU_2i3DUZ8o6H8hhMZNJXV3ueeM5i4ven2e34gYgjZrEHLkTu43PXTJhGHdx5YFvlUeLuy8dtbPg9oTBONoT465fXmoOxtS2Su8?purpose=fullsize)

**Flow:**

1. Developer pushes code → Git
2. Jenkins triggers build
3. Runs tests
4. Builds artifact
5. Creates Docker image
6. Deploys to server

