pipeline {
    agent any

    environment {
        NVM_DIR = "${WORKSPACE}/.nvm"
    }

    stages {
        stage('Prepare') {
            steps {
                sh '''
                    mkdir -p "$NVM_DIR"
                    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
                    export NVM_DIR="$WORKSPACE/.nvm"
                    [ -s "$NVM_DIR/nvm.sh" ] && \\. "$NVM_DIR/nvm.sh"
                    nvm install 22
                    node -v
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                    export NVM_DIR="$WORKSPACE/.nvm"
                    [ -s "$NVM_DIR/nvm.sh" ] && \\. "$NVM_DIR/nvm.sh"
                    npm -v
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'echo $JENKINS_URL'
            }
        }
    }
}
