## Installation

### Setting up OWASP Dependency Check in Jenkins

To download and set up OWASP Dependency Check in Jenkins, you can follow these steps:

1. Open Jenkins and navigate to the Jenkins home page.

2. Click on "Manage Jenkins" in the left-hand sidebar.

3. Select "Manage Plugins" from the options.

4. In the "Available" tab, search for "OWASP Dependency-Check Plugin" in the filter box.

5. Check the checkbox next to the plugin and click on the "Install without restart" button.

6. Once the installation is complete, go back to the Jenkins home page.

7. Click on "New Item" in the left-hand sidebar to create a new Jenkins job.

8. Enter a name for your job and select the type of job you want to create (e.g., Freestyle project or Pipeline).

9. Configure the job as per your requirements (e.g., source code management, build triggers, etc.).

10. Scroll down to the "Build" section and click on the "Add build step" dropdown.

11. Select "Invoke OWASP Dependency-Check" from the dropdown.

12. Configure the plugin settings according to your needs. This includes specifying the path to your project, any additional arguments, and choosing the appropriate OWASP Dependency-Check installation.

13. Save the job configuration.

Now, whenever you run the Jenkins job, OWASP Dependency Check will be invoked to analyze your project's dependencies for vulnerabilities.

Note: Before running the job, make sure you have already set up the desired OWASP Dependency-Check installation in Jenkins. You can do this by going to "Manage Jenkins" > "Global Tool Configuration" and adding a new installation for OWASP Dependency Check.

### Option 1: Downloading the Standalone JAR

1. Go to the [OWASP Dependency Check releases page](https://github.com/jeremylong/DependencyCheck/releases).
2. Download the latest version of the standalone JAR file (`dependency-check.jar`).
3. Ensure you have Java 8 or higher installed on your system.
4. Run the tool using the following command:
   ```
   java -jar dependency-check.jar --project <project-name> --scan <path-to-project>
   ```
### Option 2: Downloading the git using wget and unzip

1. Go to the [OWASP Dependency Check releases page](https://github.com/jeremylong/DependencyCheck/releases).
2. Download the latest version of the standalone JAR file (`dependency-check.jar`).
3. Ensure you have Java 8 or higher installed on your system.
4. Run the tool using the following command:
   ```
  wget https://github.com/jeremylong/DependencyCheck/releases/download/v9.2.0/dependency-check-9.2.0-release.zip
   ```
   ```
   sudo yum install unzip
   ```
   ```
   unzip dependency-check-9.2.0-release.zip
   ```
   ```
   rm -rf dependency-check-9.2.0-release.zip
   ```
   

### Option 2: Using Package Managers

OWASP Dependency Check is available in popular package managers:

- **Maven**: Add the following plugin to your `pom.xml` file:
  ```xml
  <build>
    <plugins>
      <plugin>
        <groupId>org.owasp</groupId>
        <artifactId>dependency-check-maven</artifactId>
        <version>INSERT_VERSION_HERE</version>
        <executions>
          <execution>
            <goals>
              <goal>check</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>
  ```
  Run `mvn dependency-check:check` to analyze your project.



## Usage

Once you have OWASP Dependency Check installed, you can run it against your project to identify vulnerabilities in dependencies.

- For the standalone JAR:
  ```
  java -jar dependency-check.jar --project <project-name> --scan <path-to-project>
  ```

- For Maven:
  ```
  mvn dependency-check:check
  ```


Make sure to replace `<project-name>` with the name of your project and `<path-to-project>` with the path to your project's directory.

## Configuration

OWASP Dependency Check offers various configuration options to customize its behavior. Refer to the [Configuration Guide](link-to-configuration-guide) for detailed information on how to configure the tool according to your needs.

## Reporting

OWASP Dependency Check generates comprehensive reports about the vulnerabilities identified in your project's dependencies. You can find the generated reports in the following locations:

- For the standalone JAR: `<path-to-project>/target/dependency-check-report.html`
- For Maven: `<path-to-project>/target/dependency-check-report.html`
- For Gradle: `<path-to-project>/build/reports/dependency-check-report.html`

Open the HTML report in your web browser to view the vulnerability details.

## Contributing

If you encounter any issues or would like to contribute to OWASP Dependency Check, please refer to the [Contributing Guidelines](link-to-contributing-guidelines) for instructions on how to get involved.

## Resources

- [OWASP Dependency Check GitHub Repository](https://github.com/jeremylong/DependencyCheck)
- [OWASP Dependency Check Official Website](https://owasp.org/www-project-dependency-check/)
