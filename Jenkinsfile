pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "building stage using build automation tool Maven"
            }
        }
       
        stage('Test') {
            steps {
                echo "unit tests"
                echo "use JUnit Jenkins plugin to do unit testing (assumption code is testing Java)"
                echo "integration tests"
                echo "use Selenium to test integration"
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
                echo "Check the quality of the Code using PMD"
            }
        }

        stage('Security Scan') {
            steps {
                echo "run second code scan using SonarQube"
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
        
        stage('Deploy') {
            steps {
                echo "deploy the application to staging server's AWS EC2 Instance"
            }
        }

        stage('Approval') {
            steps {
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
