pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --v'
            }
	stage('Deploy') {
             steps {
                 sh 'cp docker/docker-compose.yml ./docker-compose.yml'
                 sh """docker \\
                         | -H 10.1.2.27:2376 \\
                         | login \\
                         | -u root \\
                         | -p @four123# """.stripMargin()
                           

                  sh """docker \\
                         | -H 10.1.2.27:2376 \\
                         | stack deploy \\
                         | --compose-file=./docker-compose.qa.yml \\
                         | --prune \\
                         | --with-registry-auth \\
                         | Servi""".stripMargin()
	    }
        }
    }
}
