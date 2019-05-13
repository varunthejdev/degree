pipeline {
    agent any
    stages {
      stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -f Dockerfile -t varunbhupathi/degree53:latest .'
      }
      stage('Docker Push') {
      agent any
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
          sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push varunbhupathi/degree53:latest'
        }
      }
    }
  }
}
}
     
