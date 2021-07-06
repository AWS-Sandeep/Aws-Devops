pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }
         
	    
	 // Stage3 : Publish the artifacts to Nexus
        stage ('Publish to Nexus'){
            steps {
     
           nexusArtifactUploader artifacts: [[artifactId: 'sandeep', classifier: '', file: 'target/sandeep-0.0.10.war', type: 'war']], credentialsId: '0b42fd18-85c4-4dad-ac56-332b7d6d0505', groupId: 'com.sandeep', nexusUrl: '172.20.10.205:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'sandeep-SNAPSHOT', version: '0.0.10'
            }
        }
	    
        //Satge3 : Deploy
		 stage ('Deploy'){
            steps {
                echo ' Deploying......'

            }
        }
  		
        
    }

}
