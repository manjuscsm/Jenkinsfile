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
		input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
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

