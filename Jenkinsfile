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
                    sh 'kubectl delete deployments --ignore-not-found=true -n ${namespace} --selector app=mynginx  --grace-period=10'
                    sh 'kubectl delete svc --ignore-not-found=true -n ${namespace} --selector app=mynginx  --grace-period=10'
                    sh 'kubectl apply -f nginx.yaml'
                    
                }
            }
        }
    }
}
