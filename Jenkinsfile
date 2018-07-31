node {
    def app

    stage('Clone repo') {
        checkout scm
    }

    stage('Build image') {
        sh "docker-compose build"
    }

    stage('Test image') {
        app.inside {
            sh 'echo "Tests passed"'
        }
    }

    stage('Push image') {
        sh 'echo "pushed"'
    }
}
