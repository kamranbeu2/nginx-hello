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
                    sh 'kubectl create -f nginx.yaml'
                    
                }
            }
        }
    }
}
