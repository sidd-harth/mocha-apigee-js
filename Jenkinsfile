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
          //istanbul report --root $WORKSPACE --dir $WORKSPACE/coverage
          cobertura coberturaReportFile: '$WORKSPACE/coverage/*.xml'
        }
    }
}