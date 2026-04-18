# Lab 1: Building and Packaging Java Applications with Gradle
![Lab 1 Screenshot](Screenshots/Screenshot%20from%202026-04-18%2004-32-14.png)

## Steps Completed

---

### ✅ Step 1: Clone & Explore Project Structure
![Run Unit Tests](Screenshots/screen1.png)


After cloning the source code from [https://github.com/Ibrahim-Adel15/build1.git](https://github.com/Ibrahim-Adel15/build1.git), the project structure was explored using the `tree` command. The project follows a standard Gradle layout:
- `src/main/java/com/ivolve/App.java` — Main application source file
- `src/test/java/com/ivolve/AppTest.java` — Unit test file


---

### ✅ Step 2: Run Unit Tests
![Run the Application](Screenshots/screen2.png)


Unit tests were executed using the Gradle wrapper command:
```bash
./gradlew test
```
Both `compileJava` and `compileTestJava` tasks completed successfully. The build finished with **BUILD SUCCESSFUL** in 3 seconds with 3 actionable tasks executed.

---

### ✅ Step 3: Run the Application
![Run the Application](Screenshots/screen3.png)


The packaged JAR artifact was executed using:
```bash
java -jar build/libs/ivolve-app.jar
```
The application ran successfully and printed the expected output:
```
Hello iVolve Trainee
```

---

