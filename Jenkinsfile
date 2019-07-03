pipeline {
 agent any
 tools {
  maven 'M2'
  jdk 'JDK'
  nodejs 'NODEJS'
 }
 stages {


  stage('mocha test') {
   steps {
    bat "npm -v"
    bat "npm install"
    //bat "npm install -g apigeelint"
    bat "npm test"
    bat "npm run coverage"
   }
  }
 }

 post {
        always {
          step([$class: 'CoberturaPublisher', coberturaReportFile: 'Z:/Jenkins3/workspace/mocha-apigee-js/coverage/cobertura-coverage.xml'])
        }
      }
}