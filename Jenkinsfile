pipeline {
    agent none
    tools {
		jdk 'LocalJDK8' 
		maven 'LocalMaven'
	}
    stages {
	     stage('Build') {
			agent {
				 label "build"
			}
			steps {
			   echo "Build"
			   git 'https://github.com/albrodrey/Spring3MVC'
			   bat 'mvn clean package'
			   archiveArtifacts '**/*.war'
			}
		 }
		 stage('Build y deploy') {
			agent {
				 label "deploy"
			}
			steps {
			   echo "deploy"
			   git 'https://github.com/albrodrey/Spring3MVC'
			   bat 'mvn clean package'
			   copyArtifacts filter: '**/*.war', fingerprintArtifacts: true, projectName: '13-Ejercicio-groovy', selector: permalink('lastStableBuild')
			   deploy adapters: [tomcat8(credentialsId: '0b110e49-bdbc-40ef-abfa-ef16e051b1dd', path: '', url: 'http://localhost:8082')], contextPath: null, onFailure: false, war: '**/*.war'
			}
		 }
	     stage('Quality') {
			agent {
				 label "quality"
			}
			steps {
			   echo "Quality"
			   git 'https://github.com/albrodrey/Spring3MVC'
			   bat 'mvn checkstyle:checkstyle pmd:pmd'
			   checkstyle canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: '', unstableTotalAll: '1'
			   pmd canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: '', unstableTotalAll: '1'
			}
		 }
    }
}
