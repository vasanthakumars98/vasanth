pipeline{

    agent { 'label' 'java-build'}
	
	stages{
       stage('get code from git') {
		   steps{
			   
			   git credentialsId: '631ec87d-9500-49f8-a051-f8ae78c22d16', url: 'https://github.com/vasanthakumars98/vasanth.git'
		   }  
   
      
        }
        stage('Build') {
			steps{
				
               sh '"/usr/bin/mvn" clean package'
            }
       }
       stage('Results') {
		   steps{
               junit '**/target/surefire-reports/TEST-*.xml'
		   }

       }
	   stage('deploy to DEV') {
		   steps{
               junit '**/target/surefire-reports/TEST-*.xml'
		   }

       }
	   stage('run selenium') {
		   steps{
               junit '**/target/surefire-reports/TEST-*.xml'
		   }

       }
    }
}