pipeline {
    agent any
    environment {
		//PATH = "${PATH}:${getMavenPath()}"
		DOCKER_TAG = "${getLatestCommitId()}"
		//NEXUS_HOST = "172.31.45.145:8083"
	  	//DEV_IP = "3.108.54.171"
	}
    stages {
        stage('DOCKER') {
             steps {
                                  script{
                                         //sh 'cp -r ../shared-library@2/target .'
                                         sh 'docker build . -t varunchughtech/varun-testone:four'
                                           // withCredentials([gitUsernamePassword(credentialsId: 'Jenkins_Private-Key', gitToolName: 'Default')]) {
    // some block
// } 

                                              sh 'docker login -u varunchughtech -p Reetchugh@2015   '
                                              sh 'docker push varunchughtech/varun-testone:four'
                                          //}
                                  }
        }
    }
}
}
