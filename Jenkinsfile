pipeline {
    agent any
    environment {
        PROJECT_ID = 'globalinfratech'
        CLUSTER_NAME = 'gke-stage'
        LOCATION = 'europe-west1-c'
        CREDENTIALS_ID = 'gke-stage'
    }
    stages {
        stage('Deploy to GKE') {
            steps{
                step([
                $class: 'KubernetesEngineBuilder',
                projectId: env.PROJECT_ID,
                clusterName: env.CLUSTER_NAME,
                location: env.LOCATION,
                manifestPattern: 'ubuntu-pod.yaml',
                credentialsId: env.CREDENTIALS_ID,
                verifyDeployments: true])
            }
        }
    }
}
