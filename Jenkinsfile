pipeline {
    agent {
        kubernetes {
            label 'kubectl'
            defaultContainer 'kubectl'
        }
    }
    stages{
        stage('Deploy Nginx') {
            steps {
                container('kubectl') {
                    
                    sh 'kubectl apply -f k8s/nginx.yaml'
                    sh 'kubectl rollout restart deployment/mynginx'
                    
                }
            }
        }
    }
}
