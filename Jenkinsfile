pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }
    
    stage('Deploy') {
      steps {
        ansiblePlaybook credentialsId: '9419ef0c-5510-47b9-99d0-15c4b7e78942', disableHostKeyChecking: true, installation: 'ansible', 
          inventory: '/var/lib/jenkins/workspace/spring-petclinic_main/hosts', 
          playbook: '/var/lib/jenkins/workspace/spring-petclinic_main/playbook.yaml'
      }
    }
  }
}
