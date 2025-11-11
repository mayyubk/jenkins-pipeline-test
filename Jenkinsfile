pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Starting the Build stage...'
                sh 'docker build -t my-first-image .'
                echo 'Build stage complete!'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Starting the Test stage...'
                
                // This is our new test command!
                // It runs the container and checks the file inside.
                sh 'docker run --rm my-first-image cat /usr/share/nginx/html/index.html'
                
                echo 'Test stage complete!'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'This is the Deploy stage. We will tackle this next.'
            }
        }
    }
}
