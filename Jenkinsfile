pipeline {
  agent any
  stages {
    stage('Checkout') {
      git url: 'https://github.com/Kh0st3/React-Todo-Main.git'
    }
    stage('Build') {
      npm install
      npm run build
    }
    stage('Deploy') {
      echo 'Deploy the application to your target environment.'
    }
  }
}