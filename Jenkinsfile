// Declarative approach for Jernkins Job 
pipeline {
	agent any
	stages{
		stage('Build') {
			steps {
				echo "Build"
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
