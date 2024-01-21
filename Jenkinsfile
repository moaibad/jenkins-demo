pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Build docker image
                    sh 'sudo docker build -t jenkinsdemo:1.0.0 .'
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    //Hentikan container yang berjalan
                    sh 'sudo docker stop jenkinsdemo'
                    sh 'sudo docker rm jenkinsdemo'
                    // Jalankan docker container
                    sh 'sudo docker run --name jenkinsdemo -p 5000:3000 -d jenkinsdemo:1.0.0'
                }
            }
        }
    }
}
