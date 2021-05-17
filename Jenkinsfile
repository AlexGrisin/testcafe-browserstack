node {    
    properties([
        buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '5', numToKeepStr: '5'))
    ])

    stage('checkout') {
        checkout scm
    }

    stage('build') {
        sh "npm install"
    }
  
    stage('test') {
        browserstack(credentialsId: '<browserstack') {
            sh "npm run test"
        }
    }
}