pipeline {
    agent any

    stages {
        
        stage('Build') {
            steps {
                bat 'npm update'
                bat 'npm install'
                bat 'npm run build -wd SpringReact'
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
