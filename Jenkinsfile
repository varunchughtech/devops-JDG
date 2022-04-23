pipeline {
    agent any

    stages {
        stage('DOCKER') {
             steps {
                                  script{
                                         //sh 'cp -r ../shared-library@2/target .'
                                         sh 'docker build . -t varunchughtech/varun-testone:four'
                                           //withCredentials([string(credentialsId: 'neekohslihka', variable: 'dockerhubcreds')]) {

                                              sh 'docker login -u varunchughtech -p Reetchugh@2015   '
                                              sh 'docker push varunchughtech/varun-testone:four'
                                          //}
                                  }
        }
    }
}
}
