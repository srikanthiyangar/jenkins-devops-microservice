// Declarative approach for Jernkins Job 
pipeline {
	// agent any
	agent {
		docker {
			image 'maven:3.6.3'
		}
	}
	stages{
		stage('Build') {
			steps {
				sh "mvn --version"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo "Always Executed"
		}
		success {
			echo "Only if successful"
		}
		failure {
			echo "Only if fails"
		}
	}
}
