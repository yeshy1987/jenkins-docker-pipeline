node {

  checkout scm

  echo "Git checkout done..."

  stage('Create Docker Image') {
    echo "Entering docker image stage..."	
    docker.build ("yeshy1987/jenkins-docker-pipeline:${env.BUILD_NUMBER}")
      //bat 'docker build -t mysampleimage .'


  }
  stage ('Push Image to registry') {
    docker.withRegistry ('https://index.docker.io/v1/')
    docker.push()
}

  stage ('Run Application') {
      echo "entering app running stage..."
      docker.run("-p 8081:8081")
      //bat "docker run -t -d -p 8081:8081 mysampleimage:latest"
}


}