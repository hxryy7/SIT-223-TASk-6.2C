pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running the unit tests...'
                echo 'Running the integration tests...'
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis using SonarQube...'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP ZAP...'
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to staging server ...'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to production server ...'
            }
        }
    }
    post {
        success {
            emailext subject: "Pipeline '${currentBuild.fullDisplayName}' Successful",
                      body: 'The build was successful. Congratulations!',
                      to: 'harvardaan4790.be22@chitkara.edu.in',
                      attachLog: true
        }
        failure {
            emailext subject: "Pipeline '${currentBuild.fullDisplayName}' Failed",
                      body: 'The build has failed. Please investigate.',
                      to: 'harvardaan4790.be22@chitkara.edu.in',
                      attachLog: true
        }
    }
}
