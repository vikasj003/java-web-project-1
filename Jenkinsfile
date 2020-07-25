pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '6bb5ff62-1b4e-452f-85c3-4f1e4862efba', path: '', url: 'http://localhost:8081/')], contextPath: 'javawebapp', onFailure: false, war: '**/java-web-project.war'
            }
        }
    }
}
