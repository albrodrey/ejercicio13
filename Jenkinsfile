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
                     label "build"
                }
                steps {
                        echo "Build"
                }
             }
	     stage('Quality') {
             	agent {
                     label "quality"
                }
                steps {
                        echo "Quality"
                }
             }
}
