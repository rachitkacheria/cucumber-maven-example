pipeline {
    agent any
    stages {
      stage('Build') {
          step {
             
                bat "mvn clean install"
            }
               }
       stage('UploadResults') {
           step {
               [$class: 'QTM4JResultPublisher', testToRun: 'SERVER', jiraurlserver: 'http://localhost:8080', username: 'rachit.kacheria', password: 'qmetry@123', apikeyserver: '${apikey}', formatserver: 'cucumber/json', fileserver: 'target/cucumber-json-report.json', testassethierarchyserver: 'TestCase-TestStep', labelsserver: 'cucu master', versionserver: 'version 1.11', testrunnameserver: 'demo cucu testrun for testcase level', platformserver: 'Default Platform', componentserver: 'Login', commentserver: 'master commnet', testCaseUpdateLevelServer: '2',  attachFileServer: false]       }
      }
     }
}
