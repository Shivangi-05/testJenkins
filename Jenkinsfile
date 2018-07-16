pipeline {
    agent any
    
    stages {
        stage('Deploy to QA') {
            steps {
                withCredentials([[$class: 'UsernamePasswordMultiBinding', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
                    sh 'cp docker/docker-compose.yml ./docker-compose.yml'
                    sh """docker \\
                            | -H 10.1.2.27:2376 \\
                            | login \\
                            | -u shivangi \\
                            | -p shivangi \\
                            | 192.168.5.157:5000""".stripMargin()
                }
            }
        }
    }
}
