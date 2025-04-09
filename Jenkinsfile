pipeline {
    agent any

    stages {
        stage('Клонування репозиторію') {
            steps {
                git 'https://github.com/ТВОЄ-КОРИСТУВАЧ-КОД/flask-jenkins-ci-example.git'
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
