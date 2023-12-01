pipeline {
    agent { docker {image 'maven:3.9.3-eclipse-temurin-17' }}
    stages {
        stage('Example Build') {
            steps {
				echo 'mvv --version'
                // sh 'mvn -B clean verify'
            }
        }
    }
}