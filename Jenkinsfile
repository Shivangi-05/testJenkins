node {
    checkout scm

    docker.withRegistry('http://shivangi:shivangi@192.168.5.157:5043/v2/') {

        docker.image('my-custom-image').inside {
            sh 'make test'
        }
    }
}
