node{
stage('vcs') {
   git branch: 'scripted_pipeline', url: 'https://github.com/yaswitha94/spring-petclinic.git'
}
stage('build') {
  sh 'mvn package'
}
stage('archieve artifacts') {
   junit '**/surefire-reports/*.xml'
   junit '**/surefire-reports/*.xml'
}
}