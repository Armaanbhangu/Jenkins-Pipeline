pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Using Maven for building'  // Fixed spelling of 'using' and improved message
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Using JUnit for integration testing'  // Fixed spelling of 'using' and improved message
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code using SonarQube'  // Fixed spelling of 'analysising' and improved message
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security scan with OWASP ZAP'  // Improved message
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Using deployment tools Docker'  // Improved message
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'  // Improved message
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Using Deployment tool'  // Improved message
            }
        }
    }
    
    post {
        failure {
            // Send failure email notification
            emailext subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
                      body: "The pipeline has failed. Please check the logs.",
                      to: 'jotarmaan26@gmail.com'  // Replace with the appropriate email address
        }
        success {
            // Send success email notification with attached logs
            emailext subject: "Pipeline Successful: ${currentBuild.fullDisplayName}",
                      body: "The pipeline has successfully completed. Please find the logs attached.",
                      to: 'jotarmaan26@gmail.com',  // Replace with the appropriate email address
                      attachLog: true
        }
    }
}
