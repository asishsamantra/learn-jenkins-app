pipeline {
    agent any 
     
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    args '--user root'  // Run as root to avoid permission issues
                    reuseNode true
                }
            }

            steps {
                sh '''                     
                    ls -la
                    node --version
                    npm --version
                    npm ci 
                    npm run build
                    ls -la
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Test stage'
            }
        }
    }
}
