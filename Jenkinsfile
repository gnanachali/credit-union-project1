pipeline {
  agent any
  stages {	
	stage('Maven Compile'){
		steps{
			echo 'Project compile stage'
			bat label: 'Compilation running', script: '''mvn -f credit-union-project compile'''
	       	}
	}
	
	stage('Unit Test') {
	   steps {
			echo 'Project Testing stage'
			bat label: 'Test running', script: '''mvn -f credit-union-project test'''
	       
       		}
   	}

	stage('Jacoco Coverage Report') {
        	steps{
            		jacoco()
		}
	}
       
      // stage('SonarQube'){
		//steps{
			//	bat label: '', script: '''mvn sonar:sonar \
				//-Dsonar.host.url=http://localhost:9000 \
				//-Dsonar.login=d5587fdcb880b5e02a2504fb07976f5d995e03a6'''
		//	}
   	//	}
	
	stage('Maven Package'){
		steps{
			echo 'Project packaging stage'
			bat label: 'Project packaging', script: '''mvn  package'''
		}
	} 		
    
  }
}

