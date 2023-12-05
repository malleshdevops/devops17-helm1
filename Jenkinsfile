pipeline {
    agent any

    stages {
        stage('select k8') {
            steps {
              sh 'kubectl config use-context arn:aws:eks:us-west-2:897276212041:cluster/devops17-eks-57JbjgBf'    
            
        }
        }
        stage('connect k8') {
            steps {
                sh '''
                  kubectl get nodes
                                  
                '''
            }
        }
        stage('deploy k8 files') {
            steps {
                
              sh '''
                          helm upgrade --install jenkins-test-helm helm --values -f $WORKSPACE/helm/dev-values.yaml
              '''
                
            }
        }
        stage('validate deployment') {
            steps {
                sh '''
                 kubectl get po
                 
                '''
            }
        }
    }
}
