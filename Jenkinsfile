pipeline{
    agent any

    tools{
        maven 'maven'
    }

    stages{
        stage('maven clean'){
            steps{
                bat 'mvn clean'
            }
        }

        stage('maven compile'){
            steps{
                bat 'mvn compile'
            }
        }

        stage('sonar analysis'){
            withSonarQubeEnv('sonar'){
                steps{
                bat 'mvn sonar:sonar'
                     }  
            }
        }

        stage('maven test'){
            steps{
                bat 'mvn test'
            }
        }

        stage('maven package'){
            steps{
                bat 'mvn package'
            }
        }
    }
}
