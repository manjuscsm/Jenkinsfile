pipeline {
	agent { label "slave2" }
	environment {
		branch = "production"
	}		

	stages {
			
		stage("Build") {
		environment {
		branch = "production"
		}
			steps {
				sh  '''
						echo " STAGE 1: The build stage $test"
						sleep 5
					''' 
			}
		}
		stage("test") {
			steps {
				sh  '''
						echo "STAGE 2: This is a test stage	$test"
						sleep 5
					'''
			}
		}
		stage("Deploy") {
		when {
				branch 'production*'
		}
			steps {
				sh  '''
						echo "STAGE 3: This is a deploy stage $test"
						sleep 5
					'''
			}
		}
	}
}

