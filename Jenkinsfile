pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
	stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'master', 
                url: 'https://github.com/brandonbljl/JenkinsDependencyCheckTest.git',
                credentialsId: 'jenkins-PAT'
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