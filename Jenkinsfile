node {

  checkout scm

  echo "Git checkout done..."

  stage('Create Docker Image') {
    echo "Entering docker image stage..."	

    dir('jenkins-docker-pipeline/workspace') {

      docker.build("docker build - < Dockerfile")

    }

  }

  stage ('Run Application') {
      echo "entering app running stage..."
    
      sh "docker run -i -t mysampleimage:${env.BUILD_NUMBER}"
}


}