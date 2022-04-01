pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''./mvnw package
pwd'''
      }
    }

    stage('Static Analysis') {
      steps {
        echo 'Static Analysis'
        withSonarQubeEnv('sonar') {
          sh './mvnw org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
        }

      }
    }

  }
}