pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asgbuggywebapp-1 -Dsonar.organization=asgbuggywebapp-1 -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=da2d033cc1ddd70dfd92bd98849da287412fd4cd'
			}
        } 
  }
}
