pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    sh 'sudo docker build -t jenkinsdemo:1.0.0 .'
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    // Run the Docker container
                    sh 'sudo docker run --name jenkinsdemo -p 5000:3000 -d jenkinsdemo:1.0.0'
                }
            }
        }
    }
}
