pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                // Name your image
                script {
                    def dockerImage = docker.build("myapp:${env.BUILD_ID}")

                    // dockerImage.id will be the image ID for the built image
                    echo "Built Docker image ID: ${dockerImage.id}"
                }
            }
        }

         stage('Push Docker Image') {
             steps {
                 // Ensure Docker is logged in
                 script {
                     docker.withRegistry("https://762233742154.dkr.ecr.eu-west-1.amazonaws.com/egr-agreement", "ecr:eu-west-1:1780598d-687b-4412-8ad2-6ac37b2dab16") {
                        docker.image("myapp:${env.BUILD_ID}").push()
                     }
                 }
             }
         }
    }
}