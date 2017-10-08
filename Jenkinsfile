pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'Testing..'
            
          },
          "Unit tests": {
            emailext(subject: 'Hi. its a test email', body: 'Boyd test', attachLog: true, from: 'JENKINS', to: 'sergii.ponomarov@gmail.com')
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}