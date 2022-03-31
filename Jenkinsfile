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
        withSonarQubeEnv() {
          sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
        }
      }
    }
  }
