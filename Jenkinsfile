pipeline {
    agent { label 'OPENJDK-11-JDK' }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('learning') {
            steps {
                git url: 'https://github.com/longflewtinku/nop-jenkins-dockerfile.git', 
                    branch: 'dev'
            }
        }    
        stage('Example Build') {
            steps {
                sh 'kubectl aaply -f deployment.yaml'
                     
            }
        }
    }
}