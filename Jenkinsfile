pipeline {
    agent none
    stages {
        stage('package') {
               agent { docker { 
                    image 'maven:3-alpine'
                    args '-v $HOME/.m2:/root/.m2'
                } 
            }
            steps {
                sh 'mvn clean package'
				
            }
        }
        stage('build') {
            agent any
            steps {
                sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }
        }
    }
}