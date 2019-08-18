// Powered by Infostretch 

timestamps {

node () {

	stage ('paytm-dev-freestyle - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/development']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-hub Credentials', url: 'https://github.com/ashokreddykunduru/maven-web-application.git']]]) 
	}
	stage ('paytm-dev-freestyle - Build') {
 			// Maven build step
	withMaven(maven: 'maven3.6.1') { 
 			if(isUnix()) {
 				sh "mvn clean sonar:sonar deploy " 
			} else { 
 				bat "mvn clean sonar:sonar deploy " 
			} 
 		} 
	}
}
}