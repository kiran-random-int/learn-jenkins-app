pipeline{
    agent any
    stages{
        stage('node_build'){
            agent{
                docker {
                    image 'node:16-alpine'
                    reuseNode true
                }
            }
            steps{
                cleanWs()
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
    }
}