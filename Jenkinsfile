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
                    sh 'kubectl run mynginx --image=kamran420/nginx-test:latest -n jenkins'
                    sh 'kubectl expose pod mynginx --type=LoadBalancer --port=80 -n jenkins'
                }
            }
        }
    }
}
