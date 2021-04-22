pipeline {
  parameters {
        string(name: "user", defaultValue: 'cwai96')
        password(name: "pass", defaultValue: 'SECRET')
  }
  agent any
  stages {
    stage('Build Frontend') {
        steps {
            sh "docker build -t cwai96/realworld_backend:v1.0.$BUILD_NUMBER ."
        }
    }
    stage('Deploy to Docker Hub') {
        steps {
            // sh 'docker login --username="${username}" --password="${password}"'
            sh "docker login --username=${user} --password=${pass}"
            sh "docker push cwai96/realworld_backend:v1.0.$BUILD_NUMBER"
        }
    }
  }
}