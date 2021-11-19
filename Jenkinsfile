// Powered by Infostretch 

timestamps {

node () {

	stage ('joseph-test - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-access-token', url: 'https://github.com/joseph-thomasp/testrepo-forjenkins.git']]]) 
	}
	stage ('joseph-test - Build') {
 			// Shell build step
sh """ 
touch testfile 
 """ 
	}
}
}