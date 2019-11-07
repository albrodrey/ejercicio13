pipeline {
    agent none
    stages {
	       stage('Build') {
             agent {
                     label "build"
                    }
                    steps {
                        echo "Build"
                    }
                }
                stage('Build y deploy') {
                    agent {
                        label ""
                    }
                    steps {
			    sleep 10
				echo "Task2 on Parallel"
			}
                }
            }
}
