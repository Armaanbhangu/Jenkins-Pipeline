pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
            
               echo 'using Maven for building' // Echo message indicating the use of Maven for building
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'using Junit for integration testing' // indicating the use of JUnit for integration testing
            }
        }
        stage('Code Analysis') {
            steps {
                
               echo 'analysising the code using SonarQube' // indicating code analysis using SonarQube
            }
            }
        }
        stage('Security Scan') {
            steps {
               
                echo 'security scan with OWASP ZAP' // indicating security scan using OWASP ZAP
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Use deployment tools Docker' // Echo message indicating deployment to staging using Docker
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'
            }
        }
        stage('Deploy to Production') {
            steps {
               
                echo 'Using Deployment tool' indicating deployment to production using a deployment tool
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
                        
            //archiveArtifacts artifacts: '**/build.log', onlyIfSuccessful: true
        }
    }
}
