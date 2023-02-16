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
    }
}    