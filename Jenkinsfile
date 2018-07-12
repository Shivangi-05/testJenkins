node {
    checkout scm

    docker.withServer('10.1.2.27:2376') {
        docker.image('mysql:5').withRun('-p 3306:3306') {
            /* do things */
        }
    }
}
