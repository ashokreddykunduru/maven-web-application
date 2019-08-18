// Powered by Infostretch 

timestamps {

node () {
	def maven3.6.1 = tool name: 'maven3.6.1' type: maven

	stage ('paytm-dev-freestyle - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/development']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-hub Credentials', url: 'https://github.com/ashokreddykunduru/maven-web-application.git']]]) 
	}
	stage ('paytm-dev-freestyle - Build') {
 			// Maven build step
	withMaven(maven: 'maven3.6.1') { 
 			if(isUnix()) {
				sh "{maven3.6.1}\bin\ mvn clean sonar:sonar deploy " 
			} else { 
 				bat "mvn clean sonar:sonar deploy " 
			} 
 		} 
	}
}
}
