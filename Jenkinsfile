pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building stage'
          }
        }

        stage('Test stage') {
          environment {
            localEnv = 'local env'
          }
          steps {
            echo "test conducted with ${driver_path}"
            writeFile(file: 'testlog.txt', text: "test was successful with ${localEnv}")
          }
        }

      }
    }

    stage('deploy') {
      parallel {
        stage('deploy') {
          steps {
            echo "deploying  with ${driver_path}"
          }
        }

        stage('artifacts') {
          steps {
            archiveArtifacts 'testlog.txt'
          }
        }

      }
    }

    stage('production') {
      steps {
        echo 'deploying to production'
        input(message: 'Deploy to production?', id: 'yes', ok: 'yes')
      }
    }

  }
  environment {
    driver_path = '/usr/bin/Chromedriver'
  }
}