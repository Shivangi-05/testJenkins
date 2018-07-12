pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {

                sh 'mvn --version'
            }
        }
        
       stage('Deploy to QA') {
           steps {
               docker.withRegistry('http://shivangi:shivangi@192.168.5.157:5043/v2/')  {
               sh 'cp docker/docker-compose.yml ./docker-compose.yml'
               sh 'mvn --version'}
           }
       }
    }
