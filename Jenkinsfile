pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'vinodhub.online', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'api.vinodhub.online']]) {
                    sh"kubectl apply -f deployment-service.yml"
                }
            }
        }
        
       stage('Validate') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'vinodhub.online', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'api.vinodhub.online']]) {
                    sh"kubectl get svc -n webapps"
                }
            }
        }
        /* stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://9F39F577334FF23706994135261985F2.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://9F39F577334FF23706994135261985F2.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }*/
    }
}
