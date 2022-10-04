// Declarative approach for Jernkins Job 
pipeline {
	agent any
	// agent {
	// 	docker {
	// 		// image 'maven:3.6.3'
	// 		//image 'node:13.8'
	// 	}
	// }
	stages{
		stage('Build') {
			steps {
				// sh "node --version"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "$env.BUILD_ID"
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
