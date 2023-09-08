pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                echo "Building"
                sh 'mvn clean package'
            }
            post {
                always {
                    mail to: "jotarmaan26@mail.com",
                    subject: "Build Status Email",
                    body: "Build log attached!"
                }
            }
        }

        stage("Unit and Integration Tests") {
            steps {
                echo "Running unit tests"
                sh 'mvn test' 

                echo "Running integration tests"
                sh 'mvn integration-test'
                
            }
            post {
                always {
                    mail to: "jotarmaan26@mail.com",
                    subject: "Test Status Email",
                    body: "Test log attached!"
                }
            }
        }

        stage("Code Analysis") {
    steps {
        echo "Running code analysis"
        withSonarQubeEnv('SonarQubeServer') {
            sh 'mvn sonar:sonar' 
        }
    }
}
        stage("Security Scan") {
            steps {
                echo "Performing security scan"
                // Add your security scan tool commands here
            }
            post {
                always {
                    mail to: "jotarmaan26@mail.com",
                    subject: "Security Scan Status Email",
                    body: "Security scan log attached!"
                }
            }
        }

        stage("Deploy to Staging") {
            steps {
                echo "Deploying to staging"
                // Add your deployment commands here (e.g., AWS CLI)
            }
        }

        stage("Integration Tests on Staging") {
            steps {
                echo "Running integration tests on staging"
                // Add your integration tests on staging commands here
            }
        }

        stage("Deploy to Production") {
            steps {
                echo "Deploying to production"
                // Add your deployment commands for production here (e.g., AWS CLI)
            }
        }
    }
}
