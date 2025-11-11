pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Starting the Build stage...'
                // This is the new, important command
                sh 'docker build -t my-first-image .'
                echo 'Build stage complete!'
            }
        }
        
        stage('Test') {
            steps {
                echo 'This is the Test stage.'
                // A real test would be:
                // sh 'docker run --rm my-first-image <test-command>'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'This is the Deploy stage.'
                // A real deploy would be:
                // sh 'docker push my-first-image'
            }
        }
    }
}
