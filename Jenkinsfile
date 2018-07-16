pipeline {
    stages {
        stage('Deploy to QA') {
            steps {

                    sh 'cp docker/docker-compose.yml ./docker-compose.yml'
                    sh """docker login https://192.168.5.157 -u shivangi -p shivangi"""
                
            }
        }
    }
}
