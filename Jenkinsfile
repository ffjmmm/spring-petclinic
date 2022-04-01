pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('Static Analysis') {
      steps {
        withSonarQubeEnv('sonar') {
          sh './mvnw org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
        }

      }
    }

  }
}