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
    stage("push to repo) { 
      parallel {
        stage('docker') {
          stages {
            stage('push to repo') {
              steps {
                echo "In Sequential 1"
              }
            }
          }
        }
        stage("helm") {
          stages {
            stage('push to repo') {
              steps {
                echo "In Sequential 1"
              }
            }
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





