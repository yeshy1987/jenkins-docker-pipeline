node {

  checkout scm

  echo "Git checkout done..."

  stage('Create Docker Image') {
    echo "Entering docker image stage..."	
     bat image = "docker.build ("yeshy1987/jenkins-docker-pipeline:${env.BUILD_NUMBER}")"
      //bat 'docker build -t mysampleimage .'


  }
  stage ('Push Image to registry') {
    bat "docker.withRegistry ('https://index.docker.io/v1/')"
    image.push()
}

  stage ('Run Application') {
      echo "entering app running stage..."
      bat "sampleapp = image.run("-p 8081:8081")"
      //bat "docker run -t -d -p 8081:8081 mysampleimage:latest"
}


}