pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_master')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('ContinuousBuild_master')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContinuousDeployment_master')
        {
            steps
            {
               deploy adapters: [tomcat9(credentialsId: '71c5729c-6be1-44c5-be03-ea2cd42b4fc5', path: '', url: 'http://34.207.142.238:8080/')], contextPath: 'testpath', war: '**\\*.war'
            }
        }
        }

}
