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
    }
}
