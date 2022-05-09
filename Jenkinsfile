pipeline {
	agent { label "slave2" }
	environment {
		test = "pipeline_level"
	}		

	stages {
			
		stage("Build") {
		environment {
		test = "stage_level"
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
			steps {
				sh  '''
						echo "STAGE 3: This is a deploy stage $test"
						sleep 5
					'''
			}
		}
	}
}

