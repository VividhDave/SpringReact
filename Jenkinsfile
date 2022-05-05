pipeline {
    agent any

    stages {
        
        stage('Build') {
            steps {
                bat 'npm update -wd frontend'
                bat 'npm install -wd frontend'
                bat 'npm run build -wd frontend'
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
