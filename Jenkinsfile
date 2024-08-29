pipeline{
    agent any

    stages{
        stage('Build'){
        steps{
                echo "building stage using build automation tool Maven"
            }
        }
       
        stage('Test'){
        steps{
            echo "unit tests"
            echo "use Junit Jenkins plugin to do unit testing (assumption code is testing Java)"

            echo "integration tests"
            echo "use Selenium to test integration"
            }
        }
        post{
            success{
                mail to: "jpether@deakin.edu.au",
                subject: "Jenkins Tests Build",
                body: "Tests successfully completed",
                emailext attachLog: true
            }

            failure{
                mail to: "jpether@deakin.edu.au",
                subject: "Jenkins Build",
                body: "Build Failed",
                emailext attachLog: true
            }
        }

        stage('Code Quality Check'){
        steps{
            echo "Check the quality of the Code using PMD"
            }
        }

        stage('Security Scan'){
        steps{
            echo "run second code scan using SonarQube"
            }
        }
        post{
            success{
                mail to: "jpether@deakin.edu.au",
                subject: "Jenkins Build",
                body: "Security Scan Completed",
                emailext attachLog: true
            }

            failure{
                mail to: "jpether@deakin.edu.au",
                subject: "Jenkins Build",
                body: "Build Failed",
                emailext attachLog: true
            }
        }

        stage('Deploy'){
        steps{
            echo "deploy the application to staging server's AWS Ec2 Instance"
            }
        }

        stage('Approval'){
        steps{
            echo "use Selenium to test integration"
            }
        }

        stage('Deploy to Production'){
        steps{
            echo "Deploy application to production server's AWS Ec2 Instance"
            }
        }
    }
}