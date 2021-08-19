pipeline{
    agent { label'MRS'}
    triggers {
        cron('H * * * *')        
        pollSCM('* * * * *')
    }
    parameters{
        string(name: 'BRANCH', defaultValue: 'master', description: 'Branch to build')
    }
    stages{
        stage('scm'){
            steps{
                git branch: "${params.BRANCH}", url: 'https://github.com/Pruthviraj-Panda/game-of-life.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn package'
            }            
        }
    }
    post{
        success{
            archive '**/*.war'
            junit '**/TEST-*.xml'
        }
    }
}
 