pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/tanmaygupta7781/tomcat.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy WAR') {
            steps {
                // Copy WAR to Tomcat's webapps folder using sudo
                sh 'sudo cp target/MymavenWebApp01.war /opt/tomcat/webapps/'
            }
        }
    }
}
