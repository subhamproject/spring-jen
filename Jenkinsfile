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
       JAVA_HOME = "/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.252.b09-2.amzn2.0.1.x86_64/jre/bin/java"
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
