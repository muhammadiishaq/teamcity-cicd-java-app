# Java App Test Project with CI/CD using TeamCity, GitHub & DockerHub

This is a small Java application built with Gradle to demonstrate a complete CI/CD pipeline.  
The pipeline uses **TeamCity**, **GitHub**, and **DockerHub** to automatically build, version, and deploy Docker images whenever new code changes are pushed.

---

## 📦 Project Structure

```plaintext
.
├── build.gradle
├── deployment.yaml
├── Dockerfile
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew
├── gradlew.bat
├── README.md
├── settings.gradle
├── src
│   └── main
│       ├── java
│       │   └── com
│       │       └── example
│       │           └── App.java
│       └── resources
│           ├── application.properties
│           └── logback.xml
├── text.txt
└── trigger_test.txt
```

---

## 🚀 CI/CD Workflow

Here’s what happens step by step:

✅ Push code to **GitHub** repository  
✅ **TeamCity** automatically pulls the latest code whenever new changes are pushed  
✅ TeamCity builds the project using Gradle  
✅ TeamCity builds a Docker image using the `Dockerfile`  
✅ The Docker image is tagged with a version number (like `v1.0`, `v1.1`, etc.)  
✅ The new image is automatically pushed to **DockerHub**

This process keeps DockerHub always updated with the latest version of your app, without doing anything manually after pushing code.

---

## ⚙️ Tools & Technologies

- Java
- Gradle
- Docker & DockerHub
- GitHub
- TeamCity

---

## 📌 **Why this project?**

The main goal of this project is to learn and practice:
- How to automate the build and deployment process
- How to use TeamCity to create a CI/CD pipeline
- How to push versioned Docker images to DockerHub
- How to connect everything together so it works automatically when code changes

---

## ✅ How to Run Locally

Clone the repository:

```bash
git clone https://github.com/your-username/your-repo.git
```

Build the project:

```bash
./gradlew build
```

Build the Docker image:

```bash
docker build -t your-image-name:latest .
```

Run the Docker container:

```bash
docker run -p 8080:8080 your-image-name:latest
```

*(Change ports and image name if needed)*

---

## 📦 Project Summary

This is a small Java application built with Gradle, designed to demonstrate a complete CI/CD pipeline using TeamCity, GitHub, and DockerHub.

The workflow starts by pushing the project code to GitHub. In TeamCity, we manually created a build configuration that automatically pulls the latest code from GitHub whenever new changes are pushed. TeamCity then runs the Gradle build, creates a Docker image using the provided Dockerfile, and tags it with a version (e.g., v1.0, v1.1, etc.). After building, TeamCity connects to DockerHub and pushes the newly built version-tagged Docker image.

Additionally, the pipeline is configured with triggers so that any new commit to GitHub automatically starts a new build in TeamCity, creating and pushing the latest Docker image. This ensures that every code change results in an updated versioned Docker image stored in DockerHub and keeps the GitHub repository updated as the single source of truth.

This project demonstrates how to integrate source control (GitHub), build automation (TeamCity), and containerization (DockerHub) to build a robust, versioned, and automated CI/CD pipeline.

## 📌 License

This project is open-source and available under the MIT License.

---

Feel free to fork this project, try it yourself, and experiment with your own CI/CD setup! 🚀
