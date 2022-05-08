pipeline {
	agent { label "slave2" }
	stages {
			stage("Build and test") {
				parallel {
				stage("Build") {
					steps {
						sh  '''
								echo " STAGE 1: The build stage"
								sleep 5
							''' 
					}
				}
				stage("test") {
					steps {
						sh  '''
								echo "STAGE 2: This is a test stage"
								sleep 5
							'''
					}
				}
				}
				}
				stage("Deploy") {
					steps {
						sh  '''
								echo "STAGE 3: This is a deploy stage"
								sleep 5
							'''
					}
				}
	}
}

