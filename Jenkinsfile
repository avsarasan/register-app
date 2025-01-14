pipeline {
	agent {label 'Jenkins-Agent'}
	tools {
		jdk 'java17'
		maven 'maven3'
	}
	stages {
		stage ("Cleanup Workspace"){
			steps {
				cleanWs()
			}
		}
		stage ("Checkout from SCM") {
			steps {
				git branch: 'main', credentialsId: 'github', URL:'https://github.com/avsarasan/register-app' 
			}
		}
		stage ("Build Application") {
			steps {
				sh "mvn clean package"
			}
		}
	}
}
