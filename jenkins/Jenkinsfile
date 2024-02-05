pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
         stage('Manual Approval') {
            steps {
                echo '“Lanjutkan ke tahap Deploy?”'
                echo 'apakah klik Proceed (melanjutkan eksekusi pipeline ke tahap Deploy) atau Abort (menghentikan eksekusi pipeline)'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
