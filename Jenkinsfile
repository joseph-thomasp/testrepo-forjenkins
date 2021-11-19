// Powered by Infostretch 

timestamps {

node ('StandardSlave2') { 

	stage ('My-aws-cdd-dep - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-access-token', url: 'https://github.com/joseph-thomasp/testrepo-forjenkins.git']]]) 
	}
	stage ('My-aws-cdd-dep - Build') {
 			// Shell build step
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