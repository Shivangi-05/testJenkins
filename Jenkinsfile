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
               docker.withRegistry('http://10.1.2.27')  {
               sh 'cp docker/docker-compose.yml ./docker-compose.yml'
               sh 'mvn --version'}
           }
       }
    }
