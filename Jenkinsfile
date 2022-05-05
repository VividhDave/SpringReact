pipeline {
    agent any

    stages {
        
        stage('Build') {
            steps {
                bat 'npm install'
            }
        }
        
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven3.8') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven3.8') {
                    bat 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven3.8') {
                    bat 'mvn clean install -DskipTests'
                }
            }
        }
    }
}
