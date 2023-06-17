#!groovy

pipeline {
	agent none
  stages {
  	stage('Maven Install') {
    	agent {
      	docker {
        	image 'maven:3.5.0'
        }
      }
      steps {
      	sh 'mvn clean install'
      }
    }
    stage('Sonarqube') {
    	 agent any
      steps {
      	sh ''' mvn clean verify sonar:sonar \
  -Dsonar.projectKey=bpo \
  -Dsonar.projectName='bpo' \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_ec123c8964537a560081b0cb07e48a1622859a57
'''
      }
    }
    
  }
}
