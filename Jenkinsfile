@Library ('libraries')_
pipeline
{
    agent any
    stages
    {
        stage (continuiusdownload)
        {
            steps
            {
                script
                {
                     cicd.mylab("https://github.com/intelliqittrainings/maven.git")
                }
            }
        }
         stage (continuiusbuild)
        {
            steps
            {
                script
                {
                      cicd.mybuild()
                }
            }
        }
        stage (continuiusdeploy)
        {
            steps
            {
                script
                {
                      cicd.mydeploy("libraries","172.31.20.33","test23.war")
                }
            }
        }
        stage (continuiustesting)
        {
            steps
            {
                script
                {
                      cicd.mygit("https://github.com/intelliqittrainings/FunctionalTesting.git")
                      cicd.mytest()
                }
            }
        }
        stage (continuiuousdelivery)
        {
            steps
            {
                script
                {
                      cicd.mydeploy("libraries","172.31.25.112","client23.war")
                      cicd.mytest()
                }
            }
        }
    }
    
}
