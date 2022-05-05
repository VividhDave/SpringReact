pipeline {
    agent any

    stages {
        
        stage('Build') {
            steps {
                del ./frontend/package-lock.json
                bat 'npm --prefix ./frontend/ update'
                bat 'npm --prefix ./frontend/ install'
                bat 'npm --prefix ./frontend/ run build'
            }
        }

        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven3.8') {
                    bat 'mvn clean install -DskipTests=true'
                }
            }
        }
    }
}
