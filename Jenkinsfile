pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '''-----BEGIN CERTIFICATE-----
MIICwzCCAasCFBK6xKMKZkkH+vsHvBleRuhLBIz7MA0GCSqGSIb3DQEBCwUAMBgx
FjAUBgNVBAMTDWt1YmVybmV0ZXMtY2EwHhcNMjQwOTE4MTIwNjQ4WhcNMjUwOTE4
MTIwNjQ4WjAkMRAwDgYDVQQDDAdqZW5raW5zMRAwDgYDVQQKDAd3ZWJhcHBzMIIB
IjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA8jpMpDb9Xj5No6bo+Jr065vj
hvzSNH07vNmJFKsd1krfimh0hztZuW6rvcWew8Xxn9j3tIGPVJNVSySl+AG/P6Ns
B+++14XWARD8xvnM42A59HtEt/1E3XkoiTQZJTWXlFk+AO96RcTJ4MV2v3iVz4ib
sgkOtq0vRVU/Ox77OBpYw0agBc7SUv1XOiKavxQ6qexpQ1xRCJ8P7ZlIxwn13ssH
elT/QcRP4U7fzZVbSEdeiMg3KrHKsFtK0yVNugm6mzsXl+wSDohI9m/7fQG/Py+2
Z+cypmfxVawRuoonhYPHzlL5pXXSJ7z4kGFzHx3ZVy1QmQPmy9vU4VZA0JDVQwID
AQABMA0GCSqGSIb3DQEBCwUAA4IBAQA0JXz2Kn5ccVI8oMDNepOW9pChrOBhKwbL
roVu8Bdgk5G117RhT/7cUvjiG4QDmtwPuCXJjn+sAt6xqgPbcBu+jbxUKY7map6+
6Qwxt+1pWlEASoP0ZCWXnkXQbukh/NsbHJeKxw8rEnLCYN7lYgrjR6Zm/RXWK7ub
8BlSfBKyREpxYcmLxNsBJwimd8dEoIDDgVJtKWAJH6rL7Zh1py7bou6+2aYg6XDv
5pcXI3vjv8dI+vkkgDwbL6CQdP4V+9uc2rgn+aaJQavShON9GyZOPAUMKdAdudnb
rD4xW84spekBZeB5PC0xKQgXcFazP0VDrlGkjAtqmnvwVtwxGvCb
-----END CERTIFICATE-----''', clusterName: 'vinodhub.online', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'api.vinodhub.online']]) {
                    sh"kubectl apply -f deployment-service.yml"
                }
            }
        }

        
       stage('Validate') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '''-----BEGIN CERTIFICATE-----
MIICwzCCAasCFBK6xKMKZkkH+vsHvBleRuhLBIz7MA0GCSqGSIb3DQEBCwUAMBgx
FjAUBgNVBAMTDWt1YmVybmV0ZXMtY2EwHhcNMjQwOTE4MTIwNjQ4WhcNMjUwOTE4
MTIwNjQ4WjAkMRAwDgYDVQQDDAdqZW5raW5zMRAwDgYDVQQKDAd3ZWJhcHBzMIIB
IjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA8jpMpDb9Xj5No6bo+Jr065vj
hvzSNH07vNmJFKsd1krfimh0hztZuW6rvcWew8Xxn9j3tIGPVJNVSySl+AG/P6Ns
B+++14XWARD8xvnM42A59HtEt/1E3XkoiTQZJTWXlFk+AO96RcTJ4MV2v3iVz4ib
sgkOtq0vRVU/Ox77OBpYw0agBc7SUv1XOiKavxQ6qexpQ1xRCJ8P7ZlIxwn13ssH
elT/QcRP4U7fzZVbSEdeiMg3KrHKsFtK0yVNugm6mzsXl+wSDohI9m/7fQG/Py+2
Z+cypmfxVawRuoonhYPHzlL5pXXSJ7z4kGFzHx3ZVy1QmQPmy9vU4VZA0JDVQwID
AQABMA0GCSqGSIb3DQEBCwUAA4IBAQA0JXz2Kn5ccVI8oMDNepOW9pChrOBhKwbL
roVu8Bdgk5G117RhT/7cUvjiG4QDmtwPuCXJjn+sAt6xqgPbcBu+jbxUKY7map6+
6Qwxt+1pWlEASoP0ZCWXnkXQbukh/NsbHJeKxw8rEnLCYN7lYgrjR6Zm/RXWK7ub
8BlSfBKyREpxYcmLxNsBJwimd8dEoIDDgVJtKWAJH6rL7Zh1py7bou6+2aYg6XDv
5pcXI3vjv8dI+vkkgDwbL6CQdP4V+9uc2rgn+aaJQavShON9GyZOPAUMKdAdudnb
rD4xW84spekBZeB5PC0xKQgXcFazP0VDrlGkjAtqmnvwVtwxGvCb
-----END CERTIFICATE-----''', clusterName: 'vinodhub.online', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'api.vinodhub.online']]) {
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
