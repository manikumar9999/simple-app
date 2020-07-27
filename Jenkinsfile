pipeline {
  agent any
  tools {
     maven 'maven3.6.3'
          }
       stages{
          stage('Build'){
             steps{
             sh script: 'mvn clean package'
          }
        }
         stage('Upload War To Nexus'){
             steps{
                nexusArtifactUploader artifacts: [
                   [
                    artifactId: 'simple-app',
                    classifier: '',
                    file: 'target/simpe-app.1.0.0.war',
                    type: 'war'
                  ]
              ],
 credentialsId: 'mani123',
 groupId: 'in.javahome',
 nexusUrl: '172.31.39.68:8081',
 nexusVersion: 'nexus3',
 protocol: 'http',
 repository: 'http://54.210.40.219:8081/repository/simpleapp-release',
 version: '1.0.0'
}
}
}
}
