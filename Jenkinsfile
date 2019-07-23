// Powered by Infostretch 

timestamps {

node () {

	stage ('newprojectfreestyle - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/development']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'f527920f-21db-4321-9a6f-62e28496e181', url: 'https://github.com/ashokreddykunduru/maven-web-application.git']]]) 
	}
	stage ('newprojectfreestyle - Build') {
 			// Maven build step
	withMaven(maven: 'mvnHome') { 
 			if(isUnix()) {
 				sh "mvn clean sonar:sonar deploy " 
			} else { 
 				bat "mvn clean sonar:sonar deploy " 
			} 
 		} 
	}
}
}