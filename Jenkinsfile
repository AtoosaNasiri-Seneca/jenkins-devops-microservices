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
        stage('Build') {
            steps {
                echo "Build"
                sh 'mvn --version'
                sh 'docker version'
                echo "$PATH"
                echo "BUILD_NUMBER - $env.BUILD_NUMBER"
                echo "JOB_NAME - $env.JOB_NAME"
                echo "BUILD_TAG - $env.BUILD_TAG"
                echo "BUILD_URL - $env.BUILD_URL"
            }
        }
        stage('Test') {
            steps {
                echo "Test"
            }
        }
        stage ('Integration Test') {
            steps {
                echo "Integration Test"
            }
        }
    }
}