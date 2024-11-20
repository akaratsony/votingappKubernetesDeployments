pipeline {
    agent any
    stages {
        stage('Creating the pods and services for the voting app') {
            steps {
                script {
                    sh 'git pull "sudo git clone https://github.com/akaratsony/votingappKubernetes.git"'
                    sh 'sudo kubectl create -f voting-app-deploy.yaml'
                    sh 'sudo kubectl create -f voting-app-service.yaml'
                    sh 'sudo kubectl create -f redis-deploy.yaml'
                    sh 'sudo kubectl create -f redis-app-service.yaml'
                    sh 'sudo kubectl create -f worker-app-deploy.yaml'
                    sh 'sudo kubectl create -f postgres-deploy.yaml'
                    sh 'sudo kubectl create -f postgres-app-service.yaml'
                    sh 'sudo kubectl create -f result-app-deploy.yaml'
                    sh 'sudo kubectl create -f result-app-service.yaml'
        
                    sh 'kubectl get replicaset'
                    sh 'kubectl get pods'
                }
            }
        }
        stage('Scale up the replicas') {
            steps {
                script {
                    sh 'sudo kubectl scale deployment voting-app-deploy --replicas=3'
                    sh 'sudo kubectl get deployments voting-app-deploy'
                    sh 'sudo kubectl get pods'
                 
                }
            }
        }
      
    }
}
