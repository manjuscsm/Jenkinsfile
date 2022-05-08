pipeline {
	agent any
	stages {
		stage("Build") {
			steps {
				sh 'echo " STAGE 1: The build stage"' 
			}
		}
		stage("test") {
			steps {
				sh 'echo "STAGE 2: This is a test stage"'
			}
		}
		stage("Deploy") {
			steps {
				sh 'echo "STAGE 3: This is a deploy stage"'
			}
		}
	}
}
