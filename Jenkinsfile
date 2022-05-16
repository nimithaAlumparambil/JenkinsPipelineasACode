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

        stage('TestLog') {
          steps {
            writeFile(file: 'logTestFile.txt', text: 'this is an automation file log')
          }
        }

      }
    }

    stage('deploy') {
      parallel {
        stage('deploy') {
          steps {
            input(message: 'Do you want to deploy?', id: 'Ok')
            echo 'Deploying to Production'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'logTestFile.txt'
          }
        }

      }
    }

  }
}