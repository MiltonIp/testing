node {
    def app

    stage('Clone repo') {
        checkout scm
    }

    stage('Build image') {
        sh "docker build -t test ."
        sh "ls"
        sh "docker images"
        sh "docker ps"
    }

    stage('Test image') {
        sh "clair-scanner -w docker-compose.yml --ip 172.18.0.4 test:latest"
        sh 'echo "Tests passed"'
    }

    stage('Push image') {
        sh 'echo "pushed"'
    }
}
