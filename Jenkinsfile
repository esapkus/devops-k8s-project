pipeline {
agent any

stages {

    stage('Checkout') {
        steps {
            git 'https://github.com/esapkus/devops-k8s-project.git'
        }
    }

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t sandipdas23/devops-k8s-project:v1 .'
        }
    }

    stage('Push Docker Image') {
        steps {
            sh 'docker push sandipdas23/devops-k8s-project:v1'
        }
    }

    stage('Deploy to Kubernetes') {
        steps {
            sh '/home/ubuntu/scripts/deploy.sh'
        }
    }
}

}
