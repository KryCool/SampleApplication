pipeline {
    agent any

    stages{
        stage("Build"){
            steps{
                sh "mvn clean install"
            }
        }

        stage("Deploy"){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'd667366f-072f-4bcc-83a3-cc6eeb608490', path: '', url: 'http://15.164.102.56:8090')], contextPath: 'tomcat path', onFailure: false, war: '**/*.war'   
            }
        }
    }
}
