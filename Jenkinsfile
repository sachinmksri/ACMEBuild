pipeline
{
    agent any
    
    stages{
        
        stage('Get code from Git')
        {
            steps{
                git 'https://github.com/sachinmksri/ACMEBuild'
            }
        }
        
        stage('Run the code')
        {
            steps{
                bat label:'', script: 'mvn clean install'
            }
        }
        
    }
    
    post
    {
        always{
          emailext body: 'Get code from Git, run via maven command, and send mail.', 
          subject: 'Running in pipeline', 
          to: 'sachinmksri.1992@gmail.com'
        }
    }
}
