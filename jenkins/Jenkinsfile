    stages {
        stage('Pull source code') {
            steps {
                echo 'Pull Code'
                sh 'git clone code'
                sh 'git pull code'
            }
        }
        stage('Build image') {
            steps {
                echo 'build image'
                sh 'docker build -t app:latest .'
            }
        }
        stage('Push image') {
            steps {
                echo 'retage image'
                sh 'docker tag nodeapp:latest gcr.io/project-gcr/app:latest'
                echo 'push image'
                sh 'docker push gcr.io/project-gcr/app:latest'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
                sh 'kubectl rollout restart deployment app-deployment -n gunawan'
            }
        }
    }
}
