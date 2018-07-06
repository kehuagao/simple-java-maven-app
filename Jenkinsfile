pipeline {
	agent any
    stages {
        stage('Build') {
            steps {
            	bat 'd:'
            	bat 'cd C:\Users\lenovo\jenkins_home\workspace\Demo'
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
