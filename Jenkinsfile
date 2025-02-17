pipeline{

 agent any
 environment{
	PATH="/opt/maven/bin:$PATH"
	}
	stages{
	  stage('Build'){
		steps{
		  sh 'mvn clean deploy'
		}
	    }
	  stage('sonarQube analysis'){
	    environment{
		scannerHome=tool 'bharath-sonarqube-scanner'
		}
		steps{
		  withSonarQubeEnv('Bharath-SonarQube-Server'){
			sh "${sonarHome}/bin/sonar-scanner"
			}
		    }
		}
	}
     }


