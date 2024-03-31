pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'khoste/react-todo-main'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: '1f794e09-84d6-4501-a2c1-11a691e87014', url: 'https://github.com/Kh0st3/React-Todo-Main.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(env.DOCKER_IMAGE)
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', '2ddfcd03-c6bb-476c-b998-b8cc3468299d') {
                        docker.image(env.DOCKER_IMAGE).push('latest')
                    }
                }
            }
        }
    }
}