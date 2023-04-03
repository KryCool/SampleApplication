pipeline {
    agent any
 
    tools {
        maven 'Maven'   
    }
//     triggers{
//         githubPush()
//     }
    
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"
            }
        }

        stage("Deploy"){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'Tomcat-loggin', path: '', url: 'http://localhost:8090')], contextPath: 'khanhtm', war: '**/*.war'
            }
        }
    }
}
