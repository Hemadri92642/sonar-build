#!groovy

pipeline {
	agent none
  stages {
  	stage('Maven build') {
    	agent {
      	docker {
        	image 'maven:3.5.0'
        }
      }
      steps {
      	sh 'mvn clean install'
      }
    }
    stage('Sonarqube build') {
    	 agent any
      steps {
      	sh ''' mvn clean verify sonar:sonar \
  -Dsonar.projectKey=sonarqube \
  -Dsonar.projectName='sonarqube' \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_122d850e48ab396bba7ce71b4801ea42bdfba9c2
'''
      }
    }
    
  }
}
