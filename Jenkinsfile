pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the portfolio website...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to server...'
                sh 'scp -i ~/.ssh/your-key.pem -r * ec2-user@your-ec2-instance:/var/www/html/'
            }
        }
    }
}
