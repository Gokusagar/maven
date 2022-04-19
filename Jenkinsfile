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
                     cicd.mygit("https://github.com/intelliqittrainings/maven.git")
                }
            }
        }
         stage (continuiusbuild)
        {
            steps
            {
                script
                {
                      cicd.mymvn()
                }
            }
        }
    }
    
}
