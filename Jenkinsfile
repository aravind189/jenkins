pipeline {
    agent any
    stages {
        stage('Setup') {
            steps {
                echo "Branch: ${env.BRANCH_NAME}"
            }
        }
        stage('Build') {
            when {
                expression {
                    return env.BRANCH_NAME == 'main' || env.BRANCH_NAME.startsWith('release/')
                }
            }
            steps {
                echo "Building only on main or release branches"
                sh 'mvn clean package'
            }
        }
    }
}
