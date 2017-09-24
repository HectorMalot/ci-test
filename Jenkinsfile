pipeline {
  agent any
  stages {
    stage('Unit Testing') {
      steps {
        sh 'rspec spec'
      }
    }
    stage('Integration testing') {
      steps {
        parallel(
          "Integration testing": {
            sh 'rake cucumber'
            
          },
          "Firefox": {
            sleep 10
            
          },
          "Chrome": {
            sleep 10
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        sh 'git push heroku master'
      }
    }
  }
}