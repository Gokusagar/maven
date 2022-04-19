@Library ('math')_
node('built-in') 
{
    stage('Continuousdownload') 
    {
      cicd.newgit("https://github.com/intelliqittrainings/maven.git")
    }
    stage('Continuousbuild') 
    {
      cicd.newbuild()
    }
    stage('Continuousdeploy') 
    {
      cicd.newdeploy("scriptedpipeline2","172.31.10.76","test456")
    }
     stage('Continuoustest') 
    {
      cicd.newgit("https://github.com/intelliqittrainings/FunctionalTesting.git")
      cicd.newtest()
    }
    stage('Continuousdelivery') 
    {
      cicd.newdeploy("scriptedpipeline2","172.31.3.124","client456")
      
    }
}
