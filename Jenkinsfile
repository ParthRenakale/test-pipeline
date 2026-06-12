pipeline {
    agent any

    stages {
        stage('Build') {
          agent{
            docker{
              image 'node:18-alpine'
              reuseNode true
            }
          }
          steps {
              sh '''
                ls -la
                node -v
                npm -v
                pwd
                exit(0)
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
                npm test
                if [ -f public/index.html ] then 
                  echo "File found"
                fi
                

              '''
          }
        }
    }
}
