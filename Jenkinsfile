node {

  checkout scm

  echo "Git checkout done..."

  stage('Create Docker Image') {
    echo "Entering docker image stage..."	

      docker.build("mysampleimage:${env.BUILD_NUMBER} - < Dockerfile")


  }

  stage ('Run Application') {
      echo "entering app running stage..."
    
      bat 'docker run -i -t mysampleimage:${env.BUILD_NUMBER}'
}


}