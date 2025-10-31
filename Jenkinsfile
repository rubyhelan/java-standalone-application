pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            // write your logic here
            steps{
            git url:'https://github.com/rubyhelan/java-standalone-application.git',branch:'main'
            }
            
        }
        stage('Build') {
            // write your logic here
             steps{
            bat 'mvn clean install'
            }
        }
        stage('Run Application') {
            // write your logic here
            steps{
            bat 'mvn exec:java -Dexec.mainClass="com.example.Main"'
            }
        }
        stage('Test') {
            // write your logic here
            steps{
            bat 'mvn test'
            }
          
        }
        
    }
}
