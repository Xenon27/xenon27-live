pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            when {
                branch 'main'
            }
            steps {
                git branch: 'main', url: 'https://github.com/Xenon27/xenon27-live.git', credentialsId: 'github-token'
            }
        }

        stage('Build and Deploy with Docker Compose') {
            when {
                branch 'main'
            }
            steps {
                sh 'docker compose down'
                sh 'docker compose up -d --build'
            }
        }
    }
}
