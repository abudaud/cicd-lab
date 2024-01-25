pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Build') {
      agent {
        node {
          label 'docker'
        }

      }
      environment {
        CI = 'true'
      }
      steps {
        sh '''steps {
                sh \'npm install\'
            }'''
        }
      }

      stage('Test') {
        agent {
          node {
            label 'docker'
          }

        }
        environment {
          CI = 'true'
        }
        steps {
          sh '''steps {
                sh \'./jenkins/scripts/test.sh\'
            }'''
          }
        }

        stage('Manual Approval') {
          agent {
            node {
              label 'docker'
            }

          }
          environment {
            CI = 'true'
          }
          steps {
            sh '''steps {
                input message: \'Lanjutkan ke tahap Deploy?\'
            }'''
            }
          }

          stage('Deploy') {
            agent {
              node {
                label 'doker'
              }

            }
            environment {
              ci = 'true'
            }
            steps {
              sh '''
            steps {
                sh \'pyinstaller --onefile sources/add2vals.py\'
            }
            post {
                success {
                    archiveArtifacts \'dist/add2vals\'
                    sleep(time: 1, unit: \'MINUTES\')
                }'''
            }
          }

        }
        environment {
          CI = 'true'
        }
      }