// Powered by Infostretch 

timestamps {

node ('StandardSlave2') { 

	stage ('my-test-git - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: 'master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-access-token', url: 'https://github.com/joseph-thomasp/testrepo-forjenkins.git']]]) 
	}
	stage ('my-test-git - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.ws__cleanup.PreBuildCleanup". Please verify and convert manually if required.		// Shell build step
sh """ 
env
region=us-west-2
export AWS_DEFAULT_REGION=us-west-2

BUILD_NUMBER=$ARTIFACTVERSION

echo $env

cd ${CFN_HOME} && sh  stagedeploy.sh $env $BUILD_NUMBER 
 """ 
	}
}
}