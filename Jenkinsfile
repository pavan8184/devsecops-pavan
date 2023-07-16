pipeline {
  agent any
  tools { 
        maven 'maven_3_0_5'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asgbuggywebapp-1 -Dsonar.organization=asgbuggywebapp-1 -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=da2d033cc1ddd70dfd92bd98849da287412fd4cd'
			}
        } 
	   
	   stage('RunSCAAnalysisUsingSnyk') {
              steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {		
				 sh 'mvn snyk:test -fn'
				}
			}
    }		
  }
}
