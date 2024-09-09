pipeline {
    agent any
    stages {
        stage('Build Stage') {
            steps {
                echo 'Starting build process using Maven'
                // Build tool: Maven
            }
        }
        stage('Unit & Integration Tests Stage') {
            steps {
                echo 'Executing unit tests with JUnit and integration tests with Selenium'
                // Unit Testing: JUnit, Integration Testing: Selenium
            }
        }
        stage('Code Quality Analysis') {
            steps {
                echo 'Performing code quality analysis using SonarQube'
                // Code Analysis Tool: SonarQube
            }
        }
        stage('Security Scanning') {
            steps {
                echo 'Conducting security scan with OWASP ZAP'
                // Security Scanning: OWASP ZAP
            }
        }
        stage('Staging Deployment') {
            steps {
                echo 'Deploying the application to AWS EC2 (staging environment)'
                // Deployment Tool: AWS EC2, Jenkins deploy plugin
            }
        }
        stage('Staging Integration Testing') {
            steps {
                echo 'Executing integration tests in the staging environment'
                // Integration Testing: Selenium
            }
        }
        stage('Production Deployment') {
            steps {
                echo 'Deploying the application to AWS EC2 (production environment)'
                // Deployment Tool: AWS EC2, Jenkins deploy plugin
            }
        }
    }
    post {
        success {
            mail to: 'emailaddress',
                subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - SUCCESS",
                body: "The build was successful. View details at ${env.BUILD_URL}."
        }
        failure {
            mail to: 'emailaddress',
                subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - FAILURE",
                body: "The build failed. Check details at ${env.BUILD_URL} to resolve issues."
        }
        unstable {
            mail to: 'emailaddress',
                subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - UNSTABLE",
                body: "The build is unstable. Investigate issues at ${env.BUILD_URL}."
        }
        changed {
            mail to: 'emailaddress',
                subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - CHANGED",
                body: "Build status has changed. Refer to ${env.BUILD_URL} for further information."
        }
    }
}
