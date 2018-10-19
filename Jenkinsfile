pipeline {
    agent docker { label: 'docker-agent' 
				   image 'maven:3.3.3' }
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
