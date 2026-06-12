pipeline {
    agent any

    stages {
        stage('Build') {
          agent{
            docker{
              image 'node:20-alpine'
              reuseNode true
            }
          }
          steps {
              sh '''
                node -v
                npm -v
               
                npm ci
                npm start
                

              '''
          }
        }
        stage('Test') {
          agent{
            docker{
              image 'node:18-alpine'
              reuseNode true
            }
          }
          steps {
              sh '''
               
                if [ -f public/index.html ] then 
                  echo "File found"
                fi
                

              '''
          }
        }
    }
}
