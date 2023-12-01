pipeline {
    agent any 
    environment {
        // Using returnStdout
        CC = """${sh(
                returnStdout: true,
                script: 'echo "clang"'
            )}""" 
        // Using returnStatus
        EXIT_STATUS = """${sh(
                returnStatus: true,
                script: 'exit 1'
            )}"""
    }
    stages {
        stage('Example') {
            environment {
                DEBUG_FLAGS = '-g'
            }
            steps {
                sh 'printenv'
            }
        }
		stage('Example2') {
            environment {
                DEBUG_FLAGS2 = '-g'
            }
            steps {
                sh 'printenv'
            }
        }
        stage('Example3') {
            environment {
                DEBUG_FLAGS3 = '-g'
            }
            steps {
                sh 'printenv'
            }
        }
    }
}