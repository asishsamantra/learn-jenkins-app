pipeline {
    agent any 

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    args '--user jenkins'
                    reuseNode true
                }
            }

            steps {
                sh ''' 
                    ls -la 
                    node --version 
                    npm --version
                    npm ci
                    ls -la
                '''
            }
        }
    }
}