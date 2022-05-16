pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            echo 'printing Build Operation'
          }
        }

        stage('Test') {
          steps {
            echo 'On Testing branch'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        echo 'Deploying to Production'
      }
    }

  }
}