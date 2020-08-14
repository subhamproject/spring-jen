pipeline {
    options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
    disableConcurrentBuilds()
    ansiColor('xterm')
    timestamps()
    timeout(time: 10) 
  }
    agent any
    environment {
       JAVA_HOME = "/usr/lib/jvm/java-11-openjdk-11.0.7.10-4.amzn2.0.1.x86_64"
   }
    stages{
        stage('Prepare the flow'){
            steps{
                echo 'Hi now we are preparing the flow'
            }
        }

        stage('Test our code'){
            steps{
                sh './gradlew test'
            }
        }

        stage('Build our application and create a jarfile'){
                    steps{
                        sh './gradlew build -x test'
                    }
                }

        stage('Deploy to our test environments'){
            steps{
                echo 'Deploy deploy deploy'
            }
        }
    }
}
