pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                echo "Building"
            }
            post {
                always {
                    mail to: "jotarmaan26@mail.com",
                    subject: "Build Status Email",
                    body: "Build log attached!"
                }
            }
        }

        stage("Test") {
            steps {
                echo "Testing"
            }
        }

        stage("Deploy") {
            steps {
                echo "Deploying ..."
            }
        }
    }
}
