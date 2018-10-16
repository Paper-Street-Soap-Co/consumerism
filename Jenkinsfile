pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
      }
    }
    stage('Parallel Tests') {
      failFast true
      parallel {
        stage('pytest unit tests') {
          steps {
            echo "On Branch A"
          }
        }
        stage('webdriver E2E tests') {
          steps {
            echo "On Branch B"
          }
        }
      }
    }
    stage('Sequential') {
      stages {
        stage('push to docker repo') {
          steps {
            echo "In Sequential 1"
          }
        }
        stage('update helm charts') {
          steps {
            echo "In Sequential 2"
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying..'
      }
    }
  }
}





