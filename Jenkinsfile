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
sh 'scp  /var/lib/jenkins/workspace/Multibranch/webapp/target/webapp.war vagrant@10.0.0.8:/var/lib/tomcat7/webapps/pipeqaenv.war '

}

  
      
}
