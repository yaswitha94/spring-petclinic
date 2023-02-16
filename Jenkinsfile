pipeline {
    agent any
    stages {
        stage('Source Code') {
            steps {
                git url: 'https://github.com/yaswitha94/spring-petclinic.git', 
                branch: 'main'
            }
            
        }
       stage("Build and Push"){
            steps{
                  sh 'docker image build -t yaswithaa/spc:DEV .'
                  sh 'docker image push yaswithaa/spc:DEV'
            }
       }
        stage('cluster') {
            steps{
                sh 'az group create --name forspc --location eastus'
                sh 'az aks create -g forspc -n myCluster --enable-managed-identity --node-count 1 --enable-addons monitoring --enable-msi-auth-for-monitoring  --generate-ssh-keys'
                sh 'sudo az aks install-cli'
                sh 'az aks get-credentials --resource-group forspc --name myCluster'
            }
        }
       stage('deploy'){
        steps{
            sh 'kubectl create secret docker-registry cred --docker-server=https://index.docker.io/v1/ --docker-username=yaswithaa --docker-password=Aadya@1104 --docker-email=yaswitha.t@gmail.com'
            sh 'kubectl apply -f deploy.yaml'
            
        }
       }
    }
}    