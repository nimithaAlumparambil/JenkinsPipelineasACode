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
          agent any
          environment {
            var1 = 'nimitha'
          }
          steps {
            echo 'On Testing branch $var1'
          }
        }

        stage('TestLog') {
          environment {
            LocalVariable = 'HelloLocal'
          }
          steps {
            writeFile(file: 'logTestFile.txt', text: 'this is an automation file log and local variable created is ')
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