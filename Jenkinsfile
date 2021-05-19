pipeline {

  environment {
    GITHUB_URI="https://github.com/dombett/jenkins-webdriverio-test.git"
    CREDENTIALS_ID="github-username-password"
    CREDENTIALS=credentials("dombett/******")
  }
  
  stages {
    stage('Checkout domebett/jenkins-webdriverio-test') {
      steps {
        script {
          gitCheckout "jenkins-webdriverio-test", "master"
        }
      }
    }
    
    stage('Run tests') {
      steps {
        script {
          nodejs(nodeJSInstallationName: 'node_v14.17.0_lts') {
            sh "npm install"
            sh "./node_modules/.bin/cucumber-js"
          }
        }
      }
    }
  }
}
