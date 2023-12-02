// pipeline {
//     agent { docker {image 'maven:3.9.3-eclipse-temurin-17' }}
//     stages {
//         stage('Example Build') {
//             steps {
// 				echo 'mvv --version'
//                 // sh 'mvn -B clean verify'
//             }
//         }
//     }
// }
pipeline {
    agent any
    environment {
        dockerHome = tool 'myDocker'
        mavenHome = tool 'myMaven'
        PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
    }
    stages {
        stage('Checkout') {
            steps {
                echo "Checpout"
                sh 'mvn --version'
                sh 'docker version'
                echo "$PATH"
                echo "BUILD_NUMBER - $env.BUILD_NUMBER"
                echo "JOB_NAME - $env.JOB_NAME"
                echo "BUILD_TAG - $env.BUILD_TAG"
                echo "BUILD_URL - $env.BUILD_URL"
            }
        }
        stage('Compile') {
            steps {
                echo "Compile"
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage ('Integration Test') {
            steps {
                echo "Integration Test"
                sh 'mvn failsafe:integration-test failsafe:verify'
            }
        }
    }
}