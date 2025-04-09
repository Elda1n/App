pipeline {
    agent any

    stages {
        stage('Клонування репозиторію') {
            steps {
                git branch: 'main', url: 'https://github.com/Elda1n/App'
            }
        }

        stage('Збірка Docker образу') {
            steps {
                sh 'docker build -t flask-jenkins .'
            }
        }

        stage('Запуск контейнера') {
            steps {
                sh 'docker run -d -p 5001:5000 --name flask_app flask-jenkins'
            }
        }
    }
}
