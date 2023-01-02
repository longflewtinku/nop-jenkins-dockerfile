pipeline {
    agent { label 'OPENJDK-11-JDK' }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('learning') {
            steps {
                git url: 'https://github.com/longflewtinku/nop-jenkins-dockerfile.git', 
                    branch: 'main'
            }
        }    
        stage('Example Build') {
            steps {
                sh """docker image build -t one:1.0 .
                      docker container run -d  -P one:1.0"""
                     
            }
        }
    }
}