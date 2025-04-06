pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                sh '''
                    curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
                    sudo yum install -y nodejs
                    node -v
                '''
            }
        }
        stage('Build') {
            steps {
                sh 'npm -v'
            }
        }
        stage('Test') {
            steps {
                echo "JENKINS_URL: ${env.JENKINS_URL}"
            }
        }
    }
}
