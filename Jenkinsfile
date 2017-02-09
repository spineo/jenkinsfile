node {
    try {
        stage('Checkout') {
              stage 'Checkout'
                //checkout scm: [$class: 'GitSCM', branches: [[name: '*/${GIT_BRANCH}']], userRemoteConfigs: [[url: '${GIT_URL}']]]
                checkout scm: [$class: 'GitSCM', branches: [[name: '*/master']], \
                               userRemoteConfigs: [[url: 'https://github.com/spineo/groovy-gradle-project.git']]]
        }
        
        stage('Clean') {
            sh "./gradlew clean"
        
        stage('Prepare code') {
           echo 'Prepare code'
        }

        stage('Testing') {
            echo 'Testing'
        }

        stage('Staging') {
            echo 'Deploy Stage'
        }
        stage('Deploy') {
            echo 'Deploy Stage'
        }
  } catch (e) {
    currentBuild.result = "FAILED"
    throw e
  } finally {
    echo 'Success'
  }
}
