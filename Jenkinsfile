pipeline {
  agent any
  stages {
    stage('Unit Testing') {
      steps {
        sleep 5
      }
    }
    stage('Integration testing') {
      steps {
        parallel(
          "Integration testing": {
            sleep 5
            
          },
          "Firefox": {
            sleep 10
            
          },
          "Chrome": {
            sleep 15
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying app'
        sleep 5
        echo 'Deployed!'
      }
    }
  }
}