pipeline {
	agent any
    stages {
        stage('Build') {
            steps {
            	bat 'd:'
            	bat 'cd D:/.jenkins/workspace/simple-java-maven-app'
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
                bat 'cd target/surefire-reports/'
                bat 'powershell 'ls "*.xml" | foreach-object { $_.LastWriteTime = Get-Date }''
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        
    }
}
