node('built-in') 
{
    stage('continuosdownload') 
    {
    git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('continuosbuild') 
    {
    sh 'mvn package'
    }
    stage('continuosdeploy') 
    {
    sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.10.76:/var/lib/tomcat9/webapps/test1.war'
    }
    stage('continuostesting') 
    {
    git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
    sh 'java -jar testing.jar'
    }
    stage('continuosdelivery') 
    {
    sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.3.124:/var/lib/tomcat9/webapps/client.war'
    }
}
