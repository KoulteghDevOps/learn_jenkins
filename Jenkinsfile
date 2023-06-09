pipeline {
  agent {
    node {
      label 'workstation'
    }
  }

  triggers { pollSCM('H/2 * * * *') }

  options {
    ansiColor('xterm')
  }

  parameters {
    string(name: 'PERSON', defaultValue: 'Mr Jones', description: 'Who should I say Hello to?')
  }
//   agent any
  environment {
    SAMPLE_URL="yahoo.com"
  }

  stages {
    stage('One') {
      input {
                message "Should we continue?"
                ok "Yes, we should."
                
            }
      steps {
        sh 'echo Hello-World'
        sh 'echo ${SAMPLE_URL}'
        sh 'echo PERSON - ${PERSON}'
      }
    }

    stage('Two') {
      when {
        expression {
          GIT_BRANCH == 'origin/main'
        }
      }
      steps {
        sh 'env'
      }
    }
  }

  post {
    always {
      sh 'echo Post CleanUP steps'
    }
  }

}

