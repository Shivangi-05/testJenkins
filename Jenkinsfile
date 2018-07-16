node {
    checkout scm

    docker.withServer('http://10.1.2.27:2376') {
        docker.image('test-image').withRun('-p 3306:3306') {
            /* do things */
        }
    }
}
