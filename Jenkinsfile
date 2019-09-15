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

  def mavenHome=tool name: "mavenv3.6.1", type: "maven"
  
  
   stage('version')
  {
    sh "${mavenHome}/bin/mvn --version"
  }
  
  
}
