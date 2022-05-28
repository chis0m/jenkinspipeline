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

    stage('deploy') {
      steps {
        echo 'deploying stage'
      }
    }

    stage('production') {
      steps {
        echo 'deploying to production'
      }
    }

  }
}