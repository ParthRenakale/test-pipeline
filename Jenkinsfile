pipeline {
    agent any

    stages {
        stage('Build') {
          agent{
            docker{
              image node:18-alpine
              resueNode true
            }
          }
          steps {
              sh '''
                ls -la
                

              '''
          }
        }
    }
}
