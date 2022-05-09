@Library('printuser')
getUser 'Manjunath', 'Engineer'

pipeline {
	agent { label "slave2" }
	libraries {
		lib('printuser@main')
	}	

	environment {
		branch = "production"
	}
	parameters {
		string defaultValue: 'Test', description: 'Which environment you want to deploy', name: 'Deploy_Server', trim: true
	}
	stages {
			
		stage("Build") {
		environment {
		branch = "production"
		}
			steps {
				catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
				sh  '''
						echo " STAGE 1: The build stage $Deploy_Server"
						sleep 5
						exit1
					''' 
			}
			}
		}
		stage("test") {
			steps {
				sh  '''
						echo "STAGE 2: This is a test stage	$test"
						sleep 5
						echo $NODE_NAME
						echo $JOB_NAME
						echo $BUILD_NUMBER
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

