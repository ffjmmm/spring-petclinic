pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Stage'
        sh './mvnw package'
      }
    }

    stage('Static Analysis') {
      steps {
        echo 'Static Analysis'
      }
    }

  }
}