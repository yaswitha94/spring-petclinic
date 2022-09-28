pipeline {
    agent any
    parameters {
        choice(name: 'BRANCH_TO_BUILD', choices: ['main', 'parameter_1', 'declarative_pipeline'], description: 'Pick something')
        string(name: 'MAVEN_GOAL', defaultValue: 'package', description: 'Select maven goal')
    }
    stages {
        stage('vcs') {
            steps {
               git url: 'https://github.com/yaswitha94/spring-petclinic.git', 
               branch: "${params.BRANCH_TO_BUILD}"
            }
        }
        stage('GOAL') {
            steps {
                sh "/usr/share/maven/bin/mvn ${params.MAVEN_GOAL}"
            }
        }
    }
}

