node('docker') {
    checkout scm

    docker.image('ruby').inside {
        sh 'ls -all'
    }
}