pipeline {
    agent any
    environment {
        SSH_CREDENTIALS = credentials('ssh-gem-pem')  // Use the Credential ID you set in Jenkins
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Raunak191202/cicd-portfolio-website-jenkins-docker.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the portfolio website...'
            }
        }
        stage('Deploy') {
            steps {
                sshagent(['ssh-gem-pem']) {
                    sh '''
                    scp -o StrictHostKeyChecking=no -r * ec2-user@34.229.170.23:/var/www/html/
                    '''
                }
            }
        }
    }
}
