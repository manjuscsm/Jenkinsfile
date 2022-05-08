pipeline {
	agent none
	stages {
		stage("Build") {
			agent { label "master" }
			steps {
				sh  '''
						echo " STAGE 1: The build stage"
						sleep 5
					''' 
			}
		}
		stage("test") {
			agent { label "master" }
			steps {
				sh  '''
						echo "STAGE 2: This is a test stage"
						sleep 5
					'''
			}
		}
		stage("Deploy") {
			agent { label "master" }
			steps {
				sh  '''
						echo "STAGE 3: This is a deploy stage"
						sleep 5
					'''
			}
		}
	}
}

