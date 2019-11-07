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
                        echo "Build y deploy"
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
}
