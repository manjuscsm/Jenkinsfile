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
						exit 1
					''' 
			}
		}
		stage("test") {
		when {
				branch 'production*'
		}
			steps {
				sh  '''
						echo "STAGE 2: This is a test stage	$test"
						sleep 5
					'''
			}
		}
		stage("Deploy") {
			steps {
				sh  '''
						echo "STAGE 3: This is a deploy stage $test"
						sleep 5
					'''
			}
		}
	}
}

