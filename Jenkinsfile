pipeline {
    agent any 
    stages {
        stage("Build") {
            steps {
                echo "Build the code using a build automation tool to compile and package your code. You need to specify at least one build automation tool e.g., Maven."
            }
        }
        stage("Unit and Integration tests") {
            steps {
                echo "run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected. You need to specify test automation tools for this stage."
            }
            post {
                always {
                    emailext(
                        to: "jaymartiensen@gmail.com",
                        subject: "Unit and Integration tests results ${currentBuild.currentResult}",
                        body: """The build ${currentBuild.fullDisplayName} has completed.
                             Status: ${currentBuild.currentResult}
                             See Logs for more details.""",
                        attachLog: true
                    ) 
                }
            }
        }
        stage("Code Analysis") {
            steps {
                echo "Integrate a code analysis tool to analyze the code and ensure it meets industry standards. Research and select a tool to analyze your code using Jenkins."
            }
        }
        stage("Security Scan") {
            steps {
                echo "perform a security scan on the code using a tool to identify any vulnerabilities. Research and select a tool to scan your code."
            }
            post {
                always {
                    emailext(
                        to: "jaymartiensen@gmail.com",
                        subject: "Security Scan results ${currentBuild.currentResult}",
                        body: """The build ${currentBuild.fullDisplayName} has completed.
                             Status: ${currentBuild.currentResult}
                             See Logs for more details.""",
                        attachLog: true
                    ) 
                }
            }
        }
        stage("Deploy to staging") {
            steps {
                echo "deploy the application to a staging server (e.g., AWS EC2 instance)."
            }
        }
        stage("Integration Tests on Staging") {
            steps {
                echo "run integration tests on the staging environment to ensure the application functions as expected in a production-like environment."
            }
            post {
                always {
                    emailext(
                        to: "jaymartiensen@gmail.com",
                        subject: " Integration tests results ${currentBuild.currentResult}",
                        body: """The build ${currentBuild.fullDisplayName} has completed.
                             Status: ${currentBuild.currentResult}
                             See Logs for more details.""",
                        attachLog: true
                    ) 
                }  attachLog: true
                }
            }
        }
        stage("Deploy to Production") {
            steps {
                echo "deploy the application to a production server (e.g.,AWS EC2 instance)."
            }
        }
    }
}
