pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'Building..'
            
          },
          "Check styles": {
            echo 'Style is ..... OK'
            
          }
        )
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
            
          },
          "Integration tests": {
            node(label: 'test-label') {
              echo 'Test'
            }
            
            error 'This is an error'
            
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