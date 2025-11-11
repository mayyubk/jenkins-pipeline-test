pipeline {
    // Here, we're not running on the main server.
    // We're telling Jenkins to run this pipeline
    // inside a 'busybox' container.
    agent {
        docker { image 'busybox:latest' }
    }

    stages {
        stage('Run in a container') {
            steps {
                // This command runs *inside* the busybox container
                echo 'I am running inside a Docker container!'

                // Let's prove it by running a command
                // that only exists inside the container.
                sh 'uname -a'
            }
        }
    }
}
