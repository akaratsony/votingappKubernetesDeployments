pipeline {
    agent any
    stages {
        stage('Creating the pods and services for the voting app') {
            steps {
                script {
                    sh 'git pull "sudo git clone https://github.com/akaratsony/votingappKubernetes.git"'
                    sh 'sudo kubectl create -f voting-app-pod.yaml'
                    sh 'sudo kubectl create -f voting-app-service.yaml'
                    sh 'sudo kubectl create -f redis-app-pod.yaml'
                    sh 'sudo kubectl create -f redis-app-service.yaml'
                    sh 'sudo kubectl create -f worker-app-pod.yaml'
                    sh 'sudo kubectl create -f postgres-app-pod.yaml'
                    sh 'sudo kubectl create -f postgres-app-service.yaml'
                    sh 'sudo kubectl create -f result-app-pod.yaml'
                    sh 'sudo kubectl create -f result-app-service.yaml'

                    sh 'kubectl get replicaset'
                    sh 'kubectl get pods'
                }
            }
        }

      
    }
}
