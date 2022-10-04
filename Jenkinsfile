// Declarative approach for Jernkins Job 
pipeline {
	agent any
	// agent {
	// 	docker {
	// 		// image 'maven:3.6.3'
	// 		//image 'node:13.8'
	// 	}
	// }
	environment {
		dockerHome = tool "myDocker"
		mavenHome = tool "myMaven"
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout') {
			steps {
				sh "mvn --version"
				sh "docker version"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
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
