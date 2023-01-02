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
                sh """docker image build -t one:2.0 .
                      docker image tag one:2.0 longflew/laxmitinku:2.0
                      docker image push longflew/laxmitinku:2.0
                      docker container run -d -P longflew/laxmitinku:2.0"""
                     
            }
        }
    }
}