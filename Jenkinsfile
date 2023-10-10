pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Using Maven for building'  
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Using JUnit for integration testing'  
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code using SonarQube'  
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security scan with OWASP ZAP' 
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Using deployment tools Docker'  
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'  
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Using Deployment tool'  
            }
        }
    }
    
    post {
        failure {
            // Send failure email notification
            emailext subject: "Pipeline Failed: ${currentBuild.fullDisplayName}",
                      body: "The pipeline has failed. Please check the logs.",
                      to: 'jotarmaan26@gmail.com'  
        }
        success {
            // Send success email notification with attached logs
            emailext subject: "Pipeline Successful: ${currentBuild.fullDisplayName}",
                      body: "The pipeline has successfully completed. Please find the logs attached.",
                      to: 'jotarmaan26@gmail.com',  
                      attachLog: true
        }
    }
}
