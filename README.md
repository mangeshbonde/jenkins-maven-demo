# Jenkins Maven Demo 🚀

This project demonstrates a simple **CI pipeline using Jenkins and Maven** to build a Java application, run tests, and archive the generated JAR artifact.

The repository is designed for learning **DevOps CI/CD fundamentals**.

---

## 📦 Project Overview

This project contains a simple Java application built using **Maven**.
The Jenkins pipeline performs the following steps:

1. Checkout source code from GitHub
2. Build the project using Maven
3. Run unit tests
4. Package the application into a JAR file
5. Archive the generated artifact in Jenkins

---

## 🏗 Project Structure

```
jenkins-maven-demo
│
├── pom.xml
├── Jenkinsfile
├── .gitignore
├── README.md
│
└── src
    ├── main
    │   └── java
    │       └── com/example/App.java
    │
    └── test
        └── java
            └── com/example/AppTest.java
```

---

## ⚙️ Technologies Used

* Java
* Maven
* Jenkins
* Git
* GitHub

---

## 🔧 Prerequisites

Note : EC2 instance must be c7i-flex.large where Jenkins installed,this project does not support t3.micro.

Before running this project, make sure the following tools are installed:

* Java (JDK 17 or later)
* Maven
* Jenkins
* Git

Verify installation:

```
java -version
mvn -version
git --version
```

---

# Jenkins Maven Demo 🚀

This project demonstrates a simple **CI pipeline using Jenkins and Maven** to build a Java application, run tests, and archive the generated JAR artifact.

---

# Install Maven (Ubuntu / EC2)

Update the package list:

```
sudo apt update
```

Install Maven:

```
sudo apt install maven -y
```

Verify Maven installation:

```
mvn -version
```

You should see Maven version details confirming that Maven is installed successfully.

---

# Jenkins Setup and Pipeline Execution

### 1. Configure Maven in Jenkins

1. Open Jenkins Dashboard
2. Go to **Manage Jenkins**
3. Click **Global Tool Configuration**
4. Scroll to **Maven**
5. Click **Add Maven**
6. Name it:

```
Maven-3
```

7. Enable **Install Automatically** or provide the Maven installation path.

Save the configuration.

---

### 2. Create a Pipeline Job

1. Click **New Item**
2. Enter job name:

```
jenkins-maven-demo
```

3. Select **Pipeline**
4. Click **OK**

---

### 3. Connect GitHub Repository

In the Pipeline section:

Select:

```
Pipeline script from SCM
```

SCM:

```
Git
```

Repository URL:

```
https://github.com/mangeshbonde/jenkins-maven-demo.git
```

Branch:

```
*/main
```

Script Path:

```
Jenkinsfile
```

Save the job.

---

### 4. Run the Pipeline

Click:

```
Build Now
```

Jenkins will perform the following steps:

1. Clone the repository from GitHub
2. Build the project using Maven
3. Run tests
4. Package the application into a JAR file
5. Archive the generated artifact


---

## ▶️ Running the Application Locally

Clone the repository:

```
git clone https://github.com/mangeshbonde/jenkins-maven-demo.git
```

Go to the project directory:

```
cd jenkins-maven-demo
```

Build the project:

```
mvn clean package
```

Run the generated JAR:

```
java -jar target/jenkins-maven-demo-1.0-SNAPSHOT.jar
```

---

## ⚡ Jenkins Pipeline

The Jenkins pipeline is defined in the `Jenkinsfile`.

Pipeline stages:

1. **Checkout** – Pulls the repository from GitHub
2. **Build & Test** – Runs Maven build and tests
3. **Archive Artifact** – Stores the generated JAR file in Jenkins

Example pipeline stages:

```
Checkout → Build & Test → Archive Artifact
```

---

## 📦 Build Artifact

After a successful build, the JAR file is generated in:

```
target/jenkins-maven-demo-1.0-SNAPSHOT.jar
```

Jenkins archives this artifact for future use or deployment.

---

## 🚀 CI Workflow

Developer pushes code → GitHub
↓
Jenkins detects changes
↓
Build & Test using Maven
↓
Create JAR file
↓
Archive artifact in Jenkins

---

## 📚 Learning Purpose

This project helps beginners understand:

* Maven project structure
* Jenkins pipelines
* CI workflow
* Artifact management
* Java build automation

---

## 👨‍💻 Author

**Mangesh Bonde**

GitHub:
https://github.com/mangeshbonde

---

## ⭐ If you like this project

Give the repository a **star ⭐** and use it for learning DevOps CI/CD.
