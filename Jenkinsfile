node('master') 
{
   stage('ContinuousDownload_Master') 
   {
      git 'https://github.com/intelliqittrainings/maven.git'
   }
   stage('ContinuousBuild_Master')
   {
       sh 'mvn package'
   }
   stage('ContinuousDeployment_Master')
   {
      sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.94.21:/var/lib/tomcat9/webapps/qaapp.war'
   }
   stage('ContinuousTesting_Master')
   {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
       sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
   }
   
   
   
   
}

