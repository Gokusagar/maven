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
}
