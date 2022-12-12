pipeline {
    agent any
    stages {
       stage('one') {
		steps {
			echo 'Hi, This is Amit from Mumbai Branch'
		}
	}
	   stage('two') {
		steps {
			input ('Do you want to proceed?')
	}
		}
	stage ('three') {
		when {
			not {
				branch "master"
			}
		}
		steps {
			echo "Hello"
		}
	}
	stage ('Four') {
			parallel {
				stage('Unit test') {
						   steps {
								echo "Running Unit test..."
							}
				}
				stage('Integration Test') {
						   agent {
							docker {
								reuseNode false
								image 'ubuntu'
							}
						}
						steps {
							echo 'Running the integration test..'
						}
				}
			}
}
}
}		
