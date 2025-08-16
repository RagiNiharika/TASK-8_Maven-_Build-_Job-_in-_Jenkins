## TASK-8-Run-a-Simple-Java-Maven-Build-Job-in-Jenkins

## 📌 Objective
A simple Java HelloWorld application built using **Maven** and **Jenkins**.  
This project demonstrates setting up a **CI/CD pipeline** with Jenkins Freestyle jobs.

## Tools Required:
Ec2 instance (ubuntu)
Docker
Pull the Jenkins from docker hub
# Hello Java Maven - Jenkins Build Demo

## 📂 Project Structure
hello-java-maven/
├── src/
│ └── main/
│ └── java/
│ └── HelloWorld.java
├── pom.xml
└── README.md

## 🚀 Getting Started

### 1. Prerequisites
- **Java JDK** (8 or 11)
- **Maven** (e.g., 3.8.6)
- **Jenkins** (installed locally or via Docker)
- **Git** (optional, to clone repo
  
### 2. Java Code
`src/main/java/HelloWorld.java`

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
## 3. Maven Config
pom.xml

<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.example</groupId>
  <artifactId>hello</artifactId>
  <version>1.0</version>
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.8.1</version>
        <configuration>
          <source>1.8</source>
          <target>1.8</target>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
## 4. Running Jenkins
Start Jenkins with Docker:
docker run -p 8080:8080 jenkins/jenkins:lts
Access Jenkins at http://localhost:8080

## 5. Jenkins Configuration
Go to Manage Jenkins → Global Tool Configuration
Install Maven (e.g., Maven 3.8.6)
Make sure JDK is configured
Create a New Freestyle Project (e.g., hello-java-maven)
In Build section:
Add step: Invoke top-level Maven targets
Set Goal: clean package
Save and Build Now

## 6. Expected Output
Check Console Output after build:
[INFO] BUILD SUCCESS
## The packaged .jar will be available inside:
target/hello-1.0.jar
## Run it:
java -cp target/hello-1.0.jar HelloWorld
## Expected result:
Hello, Jenkins + Maven!
## Deliverables
Java HelloWorld App ✅

## What I Learned
From this project, I gained hands-on experience with:

- Running **Jenkins** in a Docker container
- Building and packaging a Java application with **Maven**
- Setting up a **Jenkins Freestyle job** to automate builds
- Understanding how Maven generates the `.jar` file
- Running the packaged Java application through **Docker + Maven build**
- Basics of Continuous Integration (CI) workflow

