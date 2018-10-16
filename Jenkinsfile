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
stage("build and deploy on Windows and Linux") {
            parallel {
                stage("windows") {
                    stages {
                        stage("build") {
                            steps {
                                echo "blah"
                            }
                        }
                        stage("deploy") {
                            steps {
                                echo "blah"
                            }
                        }
                    }
                }

                stage("linux") {
                    stages {
                        stage("build") {
                            steps {
                                echo "blah
                            }
                        }
                        stage("deploy") {
                             steps {
                                echo "blah"
                            }
                        }
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





