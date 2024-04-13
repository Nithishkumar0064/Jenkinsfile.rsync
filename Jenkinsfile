pipeline {
    agent { label 'agent-ubuntu' }

    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Nithishkumar0064/java-example.git' 
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('test') {
            steps {
                echo 'this is test stage'
            }
        }
        stage('deploy') {
            steps {
                sh 'sudo rsync -arvh ${WORKSPACE}/target/*.war /opt/tomcat/webapps'
            }
        }
    }
}
