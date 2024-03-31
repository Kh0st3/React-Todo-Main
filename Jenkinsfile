pipeline {

    agent any

    stages {

        stage('docker build') {

            steps {
                script {
                    sh "docker build -f react-todo-main/DockerFile -t khoste/react-todo-main-${BUILD_ID} react-todo-main" 
                }
            }
        }

        stage('docker push') {
            steps {
                script {
                    sh "docker push khoste/react-todo-main-${BUILD_ID}"
                }
            }
        }


    }

}