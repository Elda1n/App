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
                script {
                    docker.build('flask-jenkins')
                }
            }
        }

        stage('Запуск контейнера') {
            steps {
                script {
                    docker.image('flask-jenkins').run('-d -p 5000:5000')
                }
            }
        }
    }
}
