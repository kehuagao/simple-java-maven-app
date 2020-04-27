pipeline {
	agent any
    stages {
        stage('Build') {
            steps {
            	bat 'E:'
            	bat 'cd E:/TestLab/JENKINS_HOME/workspace/simple-java-maven-app'
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
