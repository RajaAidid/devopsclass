pipeline{
	agent any
	triggers{
		pollSCM '*/5 * * * *'
	}
	stages {
		stage('Build'){
			steps {
			sh '''
   			ls -a
			docker --help
			docker compose up
			'''
			}
		}
		stage('Test') {
			steps {
			sh '''
			apt update
			apt upgrade -y
			apt-get install python3-pip
			python3 - m venv /venv
			. /venv/bin/activate
			pip install pytest selenium
			docker compose up
			sleep 15
			python test_devopstest.py
			'''
			}
		}
	}
}
