pipeline {
  agent {
    node {
      label 'workstation'
    }
  }

  options {
    ansiColor('xterm')
  }
//   agent any
  environment {
    SAMPLE_URL="yahoo.com"
  }

  stages {
    stage('One') {
      steps {
        sh 'echo Hello-World'
        sh 'echo ${SAMPLE_URL}'
      }
    }
  }

  post {
    always {
      sh 'echo Post CleanUP steps'
    }
  }
}