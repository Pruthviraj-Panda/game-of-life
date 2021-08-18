pipeline{
    agent { label' GOL'}
    triggers {
        cron('H * * * *')
        pollSCM('* * * * *')
    }
    stages{
        stage('scm'){
            steps{
                git branch: 'master', url: 'https://github.com/Pruthviraj-Panda/game-of-life.git'
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
 