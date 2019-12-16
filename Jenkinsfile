pipeline {
    agent any
    environment{
        JAVA_HOME="/usr/lib/jvm/jdk1.8.0_231"
    }
    stages {
        stage ('Compile Stage') {

            steps {
                echo "$JAVA_HOME"
                withMaven(maven : 'apache-maven-3.6.1') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.6.1') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Install Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.6.1') {
                    sh 'mvn install'
                }
            }
        }
    }
}
