pipeline {
    agent any 

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    // args '--user jenkins'
                    args "--user $(id -u jenkins):$(id -g jenkins)"
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