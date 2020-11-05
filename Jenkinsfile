pipeline{
    agent any
    stages{
        stage("build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("deploy"){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'ccf28aab-b494-4374-b7f1-6038f67613e1', path: '', 
                url: 'http://ec2-18-191-193-194.us-east-2.compute.amazonaws.com:8080/')],
                contextPath: 'javawebapp', war: '**/*.war'
            }
        }
    }
}
