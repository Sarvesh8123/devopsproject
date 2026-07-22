pipeline {

 

    agent any

 

    stages {

 

        stage('Checkout Code') {

            steps {

                git branch: 'main',

                url: 'https://github.com/Sarvesh8123/devopsproject.git'

            }

        }

 

        stage('Build Docker Image') {

            steps {

                sh '''

                cd app

                docker build -t devops-app .

                '''

            }

        }

 

        stage('Deploy Container') {

            steps {

                sh '''

                docker stop devops-container || true

                docker rm devops-container || true

 

                docker run -d \

                  --name devops-container \

                  -p 80:80 \

                  devops-app

                '''

            }

        }

 

    }

 

}
