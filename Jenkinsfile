node {

  checkout scm

  echo "Git checkout done..."

  stage('Create Docker Image') {
    echo "Entering docker image stage..."	

      bat 'docker build -t mysampleimage .'


  }

  stage ('Run Application') {
      echo "entering app running stage..."
    
      bat 'docker run -i -t mysampleimage'
}


}