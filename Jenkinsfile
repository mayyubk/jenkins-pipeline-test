pipeline {
    agent any

    environment {
        // Defines the ID of the credentials we saved
        DOCKER_CREDS = credentials('dockerhub-credentials') 
        
        // IMPORTANT: Replace this with your Docker Hub username
        DOCKER_USERNAME = 'ayyubkhan'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Starting the Build stage...'
                // Tag the image with the Docker Hub username
                sh "docker build -t ${env.DOCKER_USERNAME}/my-first-image ."
                echo 'Build stage complete!'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Starting the Test stage...'
                // Test the new image name
                sh "docker run --rm ${env.DOCKER_USERNAME}/my-first-image cat /usr/share/nginx/html/index.html"
                echo 'Test stage complete!'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Starting the Deploy stage...'
                
                // Securely log in to Docker Hub
                // Jenkins injects the username into DOCKER_CREDS_USR
                // and the password into DOCKER_CREDS_PSW
                sh "docker login -u ${env.DOCKER_CREDS_USR} -p ${env.DOCKER_CREDS_PSW}"
                
                // Push the image to Docker Hub
                sh "docker push ${env.DOCKER_USERNAME}/my-first-image"
                
                echo 'Deploy stage complete!'
            }
        }
    }
}
