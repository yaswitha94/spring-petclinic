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
       stage('deploy'){
        steps{
            sh 'kubectl create secret docker-registry mycred --docker-server=https://index.docker.io/v1/ --docker-username=yaswithaa --docker-password=Aadya@1104 --docker-email=yaswitha.t@gmail.com'
            sh 'kubectl apply -f deploy.yaml'
        }
       }
    }
}    