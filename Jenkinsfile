pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Build the code using Maven
                echo 'Building the code using Maven...'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                // Run unit tests using JUnit
                echo 'Running unit tests using JUnit...'
                
                // Run integration tests using Selenium
                echo 'Running integration tests using Selenium...'
            }
        }
        
        stage('Code Analysis') {
            steps {
                // Integrate SonarQube for code analysis
                echo 'Integrating SonarQube for code analysis...'
            }
        }
        
        stage('Security Scan') {
            steps {
                // Perform security scan using OWASP ZAP
                echo 'Performing security scan using OWASP ZAP...'
            }
            post {
                success {
                    emailext(

                        //attachLog: true,
                        to: "trankhanhvinh1999@gmail.com",
                        subject: "Security Scan Status: SUCCESS",
                        body: "Security scan has passed successfully."
                    )
                }
                failure {
                    emailext(
                        to: "trankhanhvinh1999@gmail.com",
                        subject: "Security Scan Status: FAILURE",
                        body: "Security scan has failed.",
                        attachLog: true
                        )
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                // Deploy to AWS EC2 instance
                echo 'Deploying the application to staging server (AWS EC2 instance)...'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on staging using Selenium
                echo 'Running integration tests on staging environment using Selenium...'
            }
            post {
                success {
                    emailext(
                        to: "trankhanhvinh1999@gmail.com",
                        subject: "Integration Tests on Staging Status: SUCCESS",
                        body: "Integration tests on staging have passed successfully.",
                        attachLog: true
                        )
                }
                failure {
                    emailext(
                        to: "trankhanhvinh1999@gmail.com",
                        subject: "Integration Tests on Staging Status: FAILURE",
                        body: "Integration tests on staging have failed.",
                        attachLog: true
                        )
                }
            }
        }
        
        stage('Deploy to Production') {
            steps {
                // Deploy to AWS EC2 instance
                echo 'Deploying the application to production server (AWS EC2 instance)...'
            }
        }
    }
}
