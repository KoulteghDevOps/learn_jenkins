pipeline {
  agent {
    node {
      label 'workstation'
    }
  }
  #agent any
  stages {
    stage('One') {
      steps {
        sh 'echo Hello-World'
      }
    }
  }

  post {
    always {
      sh 'echo Post CleanUP steps'
    }
  }
}