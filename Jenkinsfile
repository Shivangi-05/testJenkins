#!/usr/bin/env groovy

pipeline {
    stages {
        stage('Deploy to QA') {
            steps {

                    sh 'cp docker/docker-compose.yml ./docker-compose.yml'
                    sh """docker \\
                            | -H 10.1.2.27 \\
                            | login \\
                            | -u shivangi \\
                            | -p shivangi \\
                            | 192.168.5.157""".stripMargin()

                    sh """docker \\
                            | -H 10.1.2.27 \\
                            | stack deploy \\
                            | --compose-file=./docker-compose.yml \\
                            | ocetagmgmtapi""".stripMargin()
                
            }
        }
    }
}
