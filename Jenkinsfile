pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            when {
                branch 'master'
            }
            steps {
                script {
                    app = docker.build("varunbhupathi/degree53 .")
                }
            }
        }
    }
}
