pipeline {
    agent any
	/*tools {
        maven 'MAVEN HOME'
		jdk 'JAVA HOME'	
    }*/	
	
    stages {
	    stage ('Initialize') {
			steps {
                		bat 'mvn --version'
				
            }			     
        }
       stage('Package') { 
            steps {
			      echo "Dev Build"
			      bat "mvn clean compile package -DskipTests"
            }
        }
	  stage('DEPLOY TO PCF') { 
            steps {
                echo 'pivotal'
                bat "cf login -a api.run.pivotal.io -o srganesh-springboot -s development -u srganesh@hcl.com -p xxxxxx --skip-ssl-validation"
	            	bat "cf push swagger-api"
            }
        } 
     }
}
