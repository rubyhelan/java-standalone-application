pipeline {
    agent any

    tools {
        jdk 'jdk-17'
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
            bat 'mvn clean compile'
            }
        }
        stage('Run Application') {
            // write your logic here
            steps{
            bat 'start /B java -jar target\\java-standalone-application.jar'
            }
        }
        stage('Test') {
            // write your logic here
            steps{
            bat 'mvn test'
            }
                 
        }
      stage('Post Message'){
      steps{
      echo 'Build and test completed successfully!'
      }
      }
        
    }
 post{
      success{
            echo 'Pipeline executed successfully'
            }
     failure{
            echo 'pipeline failed'
                }
            }
}
