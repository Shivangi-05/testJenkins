node {
    checkout scm

    docker.withServer('http://10.1.2.27:2376') {
        sh 'docker run test-image'
    }
}
