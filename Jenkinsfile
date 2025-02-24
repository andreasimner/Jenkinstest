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

//         stage('Push Docker Image') {
//             steps {
//                 // Ensure Docker is logged in
//                 script {
//                     docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-credentials') {
//                         // Push image using previously defined image ID
//                         def app = docker.image("myapp:${env.BUILD_ID}")
//                         app.push()
//                     }
//                 }
//             }
//         }
    }
}