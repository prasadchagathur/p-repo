node{
//node('master'){

  //http://JenkinsServerIPAddress:8080/pipeline-syntax/globals#currentBuild
  //Getting the  env  global varibale values

  echo "GitHub BranhName ${env.BRANCH_NAME}"
  echo "Jenkins Job Number ${env.BUILD_NUMBER}"
  echo "Jenkins Node Name ${env.NODE_NAME}"
  
  echo "Jenkins Home ${env.JENKINS_HOME}"
  echo "Jenkins URL ${env.JENKINS_URL}"
  echo "JOB Name ${env.JOB_NAME}"
  
  properties([
    buildDiscarder(logRotator(numToKeepStr: '3')),
    pipelineTriggers([
        pollSCM('* * * * *')
    ])
  ])

 
  def mavenHome="/opt/apache-maven-3.6.1"
  
   stage('version')
  {
    sh "${mavenHome}/bin/mvn --version"
  }
  stage('checkout')
  {
    git branch: 'master', credentialsId: 'f777808d-e3c4-4456-a527-90f7bdda0e9b', url: 'https://github.com/prasadchagathur/p-repo.git'  
  }
  stage('Build')
 {
  sh "${mavenHome}/bin/mvn clean package"
 }
stage('DeplotoTomcat'){
     
     sh "cp $WORKSPACE/target/*.war /opt/apache-tomcat-9.0.24/webapps/"
   
  }
  
}
