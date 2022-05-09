pipeline{



    agent any
    tools{
        maven 'Maven_3.8.5'
    }
    stages{
          stage('Build'){
              steps{
                    sh script: 'mvn clean package'
              }
              }
              stage('Upload War to Nexus'){
                  steps{
                        nexusArtifactUploader artifacts: [

                        [ artifactId: 'maven-project',
                          classifier: '',
                          file: 'target/webapp.war', type: 'war']],
                          credentialsId: 'nexus3',
                          groupId: 'com.example.maven-project',
                          nexusUrl: '54.204.235.19:8081',
                          nexusVersion: 'nexus3',
                          protocol: 'http',
                          repository: 'helloworld-release',
                          version: '1.0.0'
                  }
          }
    }
}
