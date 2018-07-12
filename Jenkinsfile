pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('Deploy') {
            steps {
              docker.withServer('tcp://10.1.2.34:2376') {
                sh 'cp docker/docker-compose.yml ./docker-compose.yml'     
            }
        }
    }
}
