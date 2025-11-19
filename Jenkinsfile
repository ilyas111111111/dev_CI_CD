pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ilyas111111111/dev_CI_CD.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t html-project .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop html-container || true'
                sh 'docker rm html-container || true'
                sh 'docker run -d --name html-container -p 8090:80 html-project'
            }
        }
    }
}

