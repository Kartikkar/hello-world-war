pipeline {
    agent any
    stages {
        stage('checkout') { 
            steps {
              sh "git clone https://github.com/Kartikkar/hello-world-war"
            }
        }
stage('build') { 
            steps {
              sh "mvn clean package"
            }
        } 
    }
}
