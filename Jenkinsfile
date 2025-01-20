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
                git branch: 'main', url: 'https://github.com/yourusername/your-repo.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the Java project with Maven...'
                sh 'mvn clean package'
            }
        }
        stage('Run') {
            steps {
                echo 'Running the Java application...'
                sh 'java -jar target/*.jar'
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
