pipeline {
    agent any

    stages {
        stage('W/o docker') {
            steps {
                sh ''' 
                    echo "Without docker"
                    ls -al 
                    touch container_no.txt
                '''
            }
        }
        
        stage('W/ docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            
            steps {
                sh '''
                    echo "With docker"
                    ls -al 
                    touch container_yes.txt
                '''
            }
        }
    }
}
