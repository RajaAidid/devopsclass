pipeline{
	agent any
	triggers{
		pollSCM '*/5 * * * *'
	}
	stages {
		stage('Build'){
			steps {
			sh '''
   			apt update -y
			apt upgrade -y
			apt-get install python3-pip -y
			python3 - m venv /venv
   			ls -a
			'''
			}
		}
	}
}
