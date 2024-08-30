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
        post{
            always{
                   echo "send test email"
                   emailext(body: 'TEST', subject: 'Jenkins Success', to: 'petherjason@gmail.com')
                
            }
            failure{
                emailext(
                    to:'petherjason@gmail.com',
                    subject: 'Jenkins Build',
                    body: 'Build Failed')
            }
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
        post{
            success{
                emailext(
                to:"petherjason@gmail.com",
                subject: "Jenkins Build",
                body: "Security Scan Completed",)
            }
            failure{
                emailext(
                to:'petherjason@gmail.com',
                subject: 'Jenkins Build',
                body: 'Build Failed',)
            }
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
            echo "Deployment done!"
            }
        }
    }
}
