pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				// git '/home/JenkinsDependencyCheckTest'
				checkout scm
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'OWASP-Dependeny-Check-Vulnerabilites'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}