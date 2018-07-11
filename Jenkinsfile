pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --v'
            }
            
             stage('Deploy to Internal Instance') {
                 steps {
                    sh """docker \\
                            | -H 10.1.2.27:2376 \\
                            | login \\
                            | -u root \\
                            | -p @four123# \\
                           

                    sh """docker \\
                            | -H 10.1.2.27:2376 \\
                            | stack deploy \\
                            | --compose-file=./docker-compose.qa.yml \\
                            | --prune \\
                            | --with-registry-auth \\
                            | ocetagmgmtapi""".stripMargin()
                
            }
        }
    }
}
