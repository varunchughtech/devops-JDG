pipeline {
    agent any

    stages {
        stage('DOCKER') {
             steps {
                                  script{
                                         //sh 'cp -r ../shared-library@2/target .'
                                         sh 'docker build . -t neekohslihka/akhil-testone:nine'
                                           withCredentials([string(credentialsId: 'neekohslihka', variable: 'dockerhubcreds')]) {

                                              sh 'docker login -u neekohslihka -p dockerhubcreds'
                                              sh 'docker push neekohslihka/akhil-testone:nine'
                                          //}
                                  }
        }
    }
}
}
