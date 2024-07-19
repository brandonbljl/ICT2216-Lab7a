pipeline {
	agent {
		docker {
			image 'composer:latest'
			// Run Docker commands as root user
            // args '-u root'
			// args '-u 1000:1000 --entrypoint=""'
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
				sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
			}
		}
	}
	post{
		always{
			junit testResults: 'logs/unitreport.xml'
		}
	}
}