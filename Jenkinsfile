pipeline {
	agent any
    stages {
        stage('Build') {
            steps {
            	bat 'C:'
            	bat 'cd C:/Users/lenovo/jenkins_home/workspace/Demo3'
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        
    }
}
