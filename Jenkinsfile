pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            
            steps {
                sh '''
                    echo "With docker"
                    node --version
                    npm --version
                    npm ci 
                    npm run build
                    ls -al
                '''
            }
        }
    }
}
