node {
    checkout scm

    docker.withServer('tcp://10.1.2.27:2376') {
        sh 'mvn --version'
    }
}
