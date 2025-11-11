pipeline {
    agent any // We'll run this on the main Jenkins server for simplicity

    stages {
        stage('Build') {
            steps {
                echo 'This is the Build stage.'
                echo 'Here we would run "docker build"...'
            }
        }
        
        stage('Test') {
            steps {
                echo 'This is the Test stage.'
                echo 'Here we would run unit tests...'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'This is the Deploy stage.'
                echo 'Here we would push to a server...'
            }
        }
    }
}
