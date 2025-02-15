// pipeline {
//     agent any 
     
//     stages {
//         stage('Build') {
//             agent {
//                 docker {
//                     image 'node:18-alpine'
//                     reuseNode true
//                 }
//             }

//             steps {
//                 sh ''' 
//                     ls -la
//                     node --version
//                     npm --version
//                     npm ci 
//                     npm run build
//                     ls -la
//                 '''
//             }
//         }
//     }
// }

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
                    # Set correct NPM home directory
                    export NPM_CONFIG_CACHE=$(pwd)/.npm-cache
                    export HOME=$(pwd)
                    
                    ls -la
                    node --version
                    npm --version

                    # Ensure correct ownership
                    sudo chown -R $(whoami):$(whoami) $HOME/.npm-cache || true

                    # Clean install dependencies
                    npm ci 

                    # Build project
                    npm run build

                    ls -la
                '''
            }
        }
    }
}
