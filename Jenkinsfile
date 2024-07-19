pipeline {
	agent {
		docker {
			image 'composer:latest'
			// Run Docker commands as root user
            // args '-u root'
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