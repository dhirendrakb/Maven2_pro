node('master')
{
   stage('ContinuousDownload-Loans1') 
   {
       git 'https://github.com/intelliqittrainings/maven.git'
   }
   stage('ContinuousBuild-Loans1') 
   {
       sh label: '', script: 'mvn package'
   }
    stage('ContinuousDeployment-Loans1') 
   {
       sh label: '', script: '''
scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.6.65:/var/lib/tomcat8/webapps/testapp.war'''
   }
   stage('ContinuousTesting-Loans1')
   {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
   
       sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
   }
   }

