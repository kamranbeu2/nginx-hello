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
                    sh 'k run mynginx --image=kamran420/nginx-test:latest'
                    sh 'k expose pod mynginx --type=LoadBalancer --port=80'
                }
            }
        }
    }
}
