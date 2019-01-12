node('master') 
{
stage('ContinuousDownlaod') 
{
git 'https://github.com/deepak13781/maven.git'
}
stage('ContinuousBuild') 
{
sh 'mvn package'
}
stage('ContinuousDeployment') 
{
sh 'scp  /var/lib/jenkins/workspace/pipe7/webapp/target/webapp.war vagrant@10.0.0.8:/var/lib/tomcat7/webapps/pipeqaenv.war '
}
stage('ContinuousTesting') 
{
git 'https://github.com/deepak13781/TestingNew.git'
sh 'java -jar /var/lib/jenkins/workspace/pipe7/testing.jar'
}    
stage('ContinuousDelivery') 
{   
sh 'scp  /var/lib/jenkins/workspace/pipe7/webapp/target/webapp.war vagrant@10.0.0.9:/var/lib/tomcat7/webapps/pipeprodenv.war '
}

  
      
}
