pipeline {
    agent any
    environment {
		//PATH = "${PATH}:${getMavenPath()}"
		DOCKER_TAG = "${getLatestCommitId()}"
		//NEXUS_HOST = "172.31.45.145:8083"
		//DEV_IP = "172.31.6.150"
	}
    stages {
        stage('DOCKER') {
             steps {
                                  script{
                                         //sh 'cp -r ../shared-library@2/target .'
                                           //sh "docker build . -t ${NEXUS_HOST}/myweb:${DOCKER_TAG} "
			                                //}
                                           //sh 'docker build . -t neekohslihka/akhil-testone:alpha2'
                                             sh 'docker build . -t neekohslihka/akhil-testone:${DOCKER_TAG}' 
                                           withCredentials([string(credentialsId: 'dockerhub', variable: 'dockerhubcreds')]) {

                                              sh 'docker login -u neekohslihka -p $dockerhubcreds'
                                              sh 'docker push neekohslihka/akhil-testone:${DOCKER_TAG}'
                                          }
                                  }
        }
    }
}
}
//to get docker image tag as per git commit id
def getLatestCommitId(){
	//def commitId = sh returnStdout: true, script: 'git rev-parse HEAD'
	def commitId = sh script: 'git rev-parse HEAD'
	return commitId
}
//to add maven home path
def getMavenPath(){
	def mvnHome = tool name: 'maven-3', type: 'maven'
	return "${mvnHome}/bin"
}
