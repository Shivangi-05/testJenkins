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
                sh 'cp docker/docker-compose.yml ./docker-compose.yml'
                sh """docker \\
                        | -H 10.1.2.27:2376 \\
                        | --tlsverify \\
                        | --tlscacert=/site/docker/docker-ca-cert.pem \\
                        | --tlscert=/site/docker/docker-client-cert.pem \\
                        | --tlskey=/site/docker/docker-client-key.pem \\
                        | login \\
                        | -u root \\
                        | -p @four123# """.stripMargin()                
            }
        }
    }
}
