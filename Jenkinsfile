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
          steps {
            echo 'Testing stage'
          }
        }

      }
    }

    stage('test') {
      steps {
        echo '"test conducted with $(driver_path) "'
        writeFile(file: 'testlog.txt', text: 'test was successful')
      }
    }

    stage('production') {
      steps {
        echo 'deploying to production'
        input(message: 'Deploy to production?', id: 'yest')
      }
    }

  }
  environment {
    driver_path = '/usr/bin/Chromedriver'
  }
}