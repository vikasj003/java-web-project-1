pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: '3c7715c5-eb8a-48d1-ab79-aef1b35753be', path: '', 
                                          url: 'http://ec2-3-133-137-143.us-east-2.compute.amazonaws.com:8080/')], 
                    contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
       }

    }
} 
