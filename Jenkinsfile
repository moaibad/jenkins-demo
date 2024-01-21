pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Build the Docker image
                    sh 'docker build -t jenkinsdemo:1.0.0 .'
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    // Run the Docker container
                    sh 'docker run -p 5000:3000 -d jenkinsdemo:1.0.0'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run your React tests here
                    sh 'npm test'
                }
            }
        }
    }

    post {
        always {
            // Cleanup steps (e.g., stop and remove the Docker container)
            script {
                sh 'docker stop $(docker ps -q --filter ancestor=jenkinsdemo:1.0.0)'
                sh 'docker rm $(docker ps -aq --filter ancestor=jenkinsdemo:1.0.0)'
            }
        }
    }
}
