node (' GOL'){
    stage('scm'){
        git 'https://github.com/Pruthviraj-Panda/game-of-life.git'
    }
    stage('build'){
        sh 'mvn package'
    }
    stage('postbuild'){
        junit '**/TEST-*.xml'
        archive '**/*.war'
    }
}