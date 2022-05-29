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
            echo '"test conducted with $(driverpath)"'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        echo 'deploying with $(driver_path)'
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
    driverpath = '/usr/bin/Chromedriver'
  }
}