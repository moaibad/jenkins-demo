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
                    sh 'sudo docker stop $(sudo docker ps -q --filter ancestor=jenkinsdemo:1.0.0)'
                    sh 'sudo docker rm $(sudo docker ps -aq --filter ancestor=jenkinsdemo:1.0.0)'
                    // Jalankan docker container
                    sh 'sudo docker run --name -p 5000:3000 -d jenkinsdemo:1.0.0'
                }
            }
        }
    }

    post {
        always {
            //
            // script {
                
            // }
        }
    }
}
