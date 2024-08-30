pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building stage using build automation tool Maven"
            }
        }
       
        stage('Test') {
            steps {
                echo "Unit tests"
                echo "Use JUnit Jenkins plugin for unit testing (assuming code is Java)"
                echo "Integration tests"
                echo "Use Selenium for integration testing"
            }
            post {
                success {
                    emailext(
                        attachLog: true,
                        to: 'petherjason@gmail.com',
                        subject: 'Jenkins Build Success',
                        body: 'The build was successful.',
                        from: 'petherjason@gmail.com'
                    )
                }
                failure {
                    emailext(
                        attachLog: true,
                        to: 'petherjason@gmail.com',
                        subject: 'Jenkins Build Failure',
                        body: 'The build failed.',
                        from: 'petherjason@gmail.com'
                    )
                }
            }
        }
         
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code using PMD"
            }
        }

        stage('Security Scan') {
            steps {
                echo "Run security scan using SonarQube"
            }
            post {
                success {
                    emailext(
                        attachLog: true,
                        to: 'petherjason@gmail.com',
                        subject: 'Jenkins Security Scan Success',
                        body: 'The security scan was successful.',
                        from: 'petherjason@gmail.com'
                    )
                }
                failure {
                    emailext(
                        attachLog: true,
                        to: 'petherjason@gmail.com',
                        subject: 'Jenkins Security Scan Failure',
                        body: 'The security scan failed.',
                        from: 'petherjason@gmail.com'
                    )
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo "Deploy the application to staging server's AWS EC2 Instance"
            }
        }

        stage('Approval'){
        steps{
            echo "use Selenium to test integration"
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploy application to production server's AWS EC2 Instance"
                echo "Deployment done!"
            }
        }
    }
}
