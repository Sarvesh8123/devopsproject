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

               

                docker build -t devops-app .

                '''

            }

        }

 

        stage('Deploy Container') {

            steps {

                sh '''


 

                docker run -d \

                  --name devops-container \

                  -p 80:80 \

                  devops-app

                '''

            }

        }

 

    }

 

}
