#!groovy

pipeline {
	agent none
  stages {
    stage('Sonarqube build') {
    	 agent any
      steps {
      	sh ''' mvn clean verify sonar:sonar \
  -Dsonar.projectKey=sonar-build \
  -Dsonar.projectName='sonar-build' \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_ec68eaf1c959112ea45c12a24155676f6d2f6d9a
'''
      }
    }
    
  }
}
