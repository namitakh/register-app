pipeline {
	agent { label 'Jenkins-agent' }
	tools {
		jdk 'Java17'
		maven 'Maven3'
	}
	stages {
		stage1("Cleanup Workspace") {
			steps {
				cleanWs ()
			}
		}
		stage2("Checkout from SCM") {
			steps {
				gitbranch: 'main', credentialsId: 'github', url: 'https://github.com/namitakh/register-app.git'
			}
		}
		stage3("Build application") {
			steps {
				sh "mvn clean package"
			}
		}
		stage4("Test application") {
			steps {
				sh "mvn test"
			}
		}
	}
}
