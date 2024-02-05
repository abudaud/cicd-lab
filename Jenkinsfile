 pipeline {
    agent any

    environment {
        // Definisi variabel lingkungan jika diperlukan
        // Misalnya: PATH_TO_ENV_FILE = '/path/to/env/file'
    }

    stages {
        stage('Build') {
            steps {
                // Langkah-langkah untuk melakukan proses build
                // Misalnya: sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Langkah-langkah untuk melakukan proses pengujian
                // Misalnya: sh 'npm test'
            }
        }

        stage('Manual Approval') {
            steps {
                script {
                    // Menunggu persetujuan manual sebelum melanjutkan ke tahap selanjutnya
                    input 'Apakah Anda yakin ingin melanjutkan?'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Langkah-langkah untuk melakukan proses deployment
                // Misalnya: sh 'kubectl apply -f deployment.yaml'
            }
        }
    }

    post {
        success {
            // Tindakan yang akan diambil jika pipeline berhasil
            // Misalnya: Kirim notifikasi ke tim atau lakukan tindakan lanjutan
        }

        failure {
            // Tindakan yang akan diambil jika pipeline gagal
            // Misalnya: Kirim notifikasi ke tim atau lakukan tindakan pemulihan
        }

        always {
            // Tindakan yang akan diambil selalu, terlepas dari hasil pipeline
            // Misalnya: Membersihkan sumber daya atau melakukan langkah-langkah pembersihan
        }
    }
}
