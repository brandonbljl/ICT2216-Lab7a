ICT2216-Lab7a {
    agent {
        docker {
            image 'composer:latest'
        }
    }
    stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'master', 
                    url: 'https://github.com/brandonbljl/ICT2216-Lab7a.git'
            }
        }
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
