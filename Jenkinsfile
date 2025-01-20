pipeline {
    agent any
    tools {
        maven 'Maven' // Set up Maven in Jenkins (Manage Jenkins > Global Tool Configuration)
        jdk 'Java'    // Set up JDK in Jenkins
    }
    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning the repository...'
                git branch: 'master', url: 'https://github.com/aravind189/jenkins.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the Java project with Maven...'
                sh 'mvn clean package'
            }
        }
    }
    post {
        success {
            echo 'Build and run were successful!'
        }
        failure {
            echo 'Build or run failed. Check the logs.'
        }
    }
}
