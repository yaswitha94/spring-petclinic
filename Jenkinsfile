pipeline {
    agent any
    stages {
        stage('Getting code') {
            steps {
                git url: 'https://github.com/yaswitha94/spring-petclinic.git', 
                    branch: 'declarative_pipeline'
                    sh 'mvn package'
            }
            
               
        }
    }
}