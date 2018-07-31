node {
    def app

    stage('Clone repo') {
        checkout scm
    }

    stage('Build image') {
        sh "docker build -t test ."
        sh "ls"
    }

    stage('Test image') {
        sh ".../clair-scanner -w docker-compose.yml --ip 172.17.0.2 test:latest"
        sh 'echo "Tests passed"'
    }

    stage('Push image') {
        sh 'echo "pushed"'
    }
}
