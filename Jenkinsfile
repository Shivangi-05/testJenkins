#!/usr/bin/env groovy

pipeline {
    agent any

    tools {
        maven   'maven-3.5.2'
        jdk     'jdk1.8.0_152'
    }

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
