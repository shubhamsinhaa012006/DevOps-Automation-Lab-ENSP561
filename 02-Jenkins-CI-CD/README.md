# Experiment 02: Jenkins CI/CD Pipeline with Nginx Deployment

## Objective
To set up Jenkins, create a Declarative Pipeline, connect it with a GitHub repository, build the project, and deploy it using Nginx on localhost.

## Software Required
- Git
- Jenkins
- Nginx
- Web Browser (Chrome / Safari / Firefox)

## Prerequisites
- A GitHub repository with the project source code.
- Jenkins installed and running locally.
- Nginx installed and running locally.

## Theory
**Continuous Integration (CI)** is a software development practice where developers regularly merge their code changes into a central repository, after which automated builds and tests are run. **Continuous Deployment (CD)** automates the release of the validated code to a repository or directly to production.

## Jenkins Architecture
Jenkins uses a Controller-Agent architecture. The Jenkins Controller server schedules build jobs, dispatches them to agents for execution, and records the results. A Declarative Pipeline provides a simplified and structured syntax to define the entire build process as code (Pipeline-as-Code) in a `Jenkinsfile`.

## Pipeline Stages
1. **Checkout:** Pulls the latest source code from the configured GitHub repository.
2. **Build:** Verifies the contents of the workspace.
3. **Test:** Checks for the presence of essential project files (e.g., README.md).
4. **Deploy:** Copies the project files to the configured Nginx web root directory to serve the application locally.

## Step-by-step Procedure
1. Open Jenkins in the web browser (`http://localhost:8080`) and log in.
2. Click on **New Item**, enter a project name, select **Pipeline**, and click **OK**.
3. In the Pipeline configuration, scroll to the **Pipeline** section.
4. Set the **Definition** to `Pipeline script from SCM`.
5. Select `Git` as the **SCM** and provide the GitHub repository URL.
6. Specify the branch to build (e.g., `*/main`).
7. Ensure the **Script Path** is set to `02-Jenkins-CI-CD/Jenkinsfile`.
8. Save the configuration and click **Build Now**.
9. Once the build succeeds, open a web browser and navigate to `http://localhost` to verify the deployment via Nginx.
   > **Note:** The deployment path in the `Jenkinsfile` is configured for the default macOS Apple Silicon Homebrew Nginx web root. Depending on your local Nginx installation, you may need to adjust this deployment path.

## Commands Used

### Git Commands
- `git clone`: Clones a repository into a newly created directory.
- `git pull`: Fetches from and integrates with another repository or a local branch.
- `git push`: Updates remote refs along with associated objects.

### Jenkins Pipeline Commands
- `checkout scm`: Checks out the source code from the version control system.
- `sh`: Executes a shell script command (e.g., `ls -la`, `cp`).
- `cleanWs()`: Cleans the Jenkins workspace after the pipeline finishes.

## Expected Output
- The Jenkins pipeline should execute all stages successfully (Checkout, Build, Test, Deploy).
- The Jenkins console output should display successful verification and deployment messages.
- The project files should be accessible locally via a web browser at `http://localhost`.

*(Insert Jenkins Pipeline Success Screenshot Here)*

*(Insert Nginx Localhost Deployment Screenshot Here)*

## Learning Outcome
- Successfully configured a Jenkins Declarative Pipeline.
- Integrated Jenkins with a GitHub repository for automated source code fetching.
- Deployed a web project locally using Nginx as a web server.

## Conclusion
This experiment successfully demonstrates the implementation of a fundamental CI/CD pipeline using Jenkins and Nginx. By defining the infrastructure as code in a Jenkinsfile, the process of building, testing, and deploying becomes automated, repeatable, and scalable.

## References
- [Jenkins Documentation](https://www.jenkins.io/doc/)
- [Nginx Documentation](https://nginx.org/en/docs/)
- [Git Official Documentation](https://git-scm.com/doc)
