pipeline {
    agent any 

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'nopde:18-alpine'
                }
            }

            steps {
                sh ''' 
                    ls -la 
                    node --version 
                    npm --version
                '''
            }
        }
    }
}