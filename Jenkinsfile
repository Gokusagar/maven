pipeline
{
    agent any
    stages
    {
        stage('continuousdownload')
        {
            steps
            {
                git 'https://github.com/Gokusagar/scriptedpeipeline.git'
            }
        }
        stage('continuousbuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
         stage('continuousdeploy')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.10.76:/var/lib/tomcat9/webapps/test12.war'
            }
        }
         stage('continuoustesting')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar testing.jar'
            }
        }
       
       stage('continuousdelivery')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.3.124:/var/lib/tomcat9/webapps/prod12.war'
            }
        }
    }
}
