pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''steps {
                sh \'npm install\'
            }'''
        }
      }

      stage('Test') {
        steps {
          sh '''steps {
                sh \'./jenkins/scripts/test.sh\'
            }'''
          }
        }

        stage('Deliver') {
          agent {
            node {
              label 'docker'
            }

          }
          environment {
            CI = 'true'
          }
          steps {
            sh ''' steps {
                sh \'./jenkins/scripts/deliver.sh\'
                input message: \'Finished using the website? (Click "Proceed" to continue)\'
                sh \'./jenkins/scripts/kill.sh\'
            }'''
            }
          }

        }
        environment {
          CI = 'true'
        }
      }