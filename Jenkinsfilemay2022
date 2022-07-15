node
{
 def mavenHome = tool name: "maven3.8.5"
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
echo "The job name is: ${env.JOB_NAME}"
echo "The node name is: ${env.NODE_NAME}"
echo "The workspace path is: ${env.WORK_SPACE}"
echo "The node label is: ${env.NODE_LABELS}"
echo "The build number is: ${env.BUILD_NUMBER}"

stage('CheckoutCode'){
git branch: 'development', credentialsId: 'b3617e55-74ba-4ad2-b939-7d3611f5ee90', url: 'https://github.com/Tejaswiniedara/maven-web-application.git'  
}
  
stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}
  
  /*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}
  
stage('UploadArtifactsIntoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}
stage('DeployAppIntoTomcatServer') {
sshagent(['2b66e1af-5d16-4fff-b539-1ba164e6cff6']) {
sh "scp -o  StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.234.37.91:/opt/apache-tomcat-9.0.64/webapps/"
}  
}
 */
  
}
