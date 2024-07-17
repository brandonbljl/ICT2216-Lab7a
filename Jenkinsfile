pipeline {
    agent {
        docker {
            image 'composer:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount the Docker socket
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'composer install'
            }
        }
        stage('Test') {
            steps {
                sh './vendor/bin/phpunit tests'
            }
        }
    }
}
