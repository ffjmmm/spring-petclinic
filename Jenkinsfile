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
        ansiblePlaybook credentialsId: '33fb492f-d44b-4ed9-862e-48582f01a62a', disableHostKeyChecking: true, installation: 'ansible', 
          inventory: '/var/lib/jenkins/workspace/spring-petclinic_main/hosts', 
          playbook: '/var/lib/jenkins/workspace/spring-petclinic_main/playbook.yaml'
      }
    }
  }
}
