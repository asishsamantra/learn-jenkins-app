pipeline {
    agent any 

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    args '--user root'
                    reuseNode true
                }
            }

            steps {
                sh ''' 
                    ls -la 
                    node --version 
                    npm --version
                    pwd
                    npm ci
                    ls -la
                '''
            }
        }
    }
}