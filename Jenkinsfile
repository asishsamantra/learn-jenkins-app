pipeline {
    agent any 

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    user '111:113'
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