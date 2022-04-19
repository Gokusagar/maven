pipeline
{
    agent any
    stages
    {
        stage(continuousdownload)
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage(continuousbuild)
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage(continuousdeploy)
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.20.33:/var/lib/tomcat9/webapps/test12.war'
            }
        }
        stage(continuoustesting)
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar testing.jar'
            }
        }
        stage(continuousdelivery)
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.25.112:/var/lib/tomcat9/webapps/client12.war'
            }
        }
    }
}
