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

 
}
