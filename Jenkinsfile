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
    stage("push to repo") { 
      parallel {
        stage('docker') {
          stages {
            stage('docker') {
              steps {
                echo "docker"
              }
            }
          }
        }
        stage("helm") {
          stages {
            stage('helm') {
              steps {
                echo "helm"
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
    stage('Validate') {
      steps {
        echo 'Validate..'
      }
    }
  }
}





