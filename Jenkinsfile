pipeline{

    agent any

    stages {
        stage("CONTINUOUS DOWNLOAD"){

            steps{
                git branch: 'main', url: 'https://github.com/nelatmani/SIELI-CICD-Nabil.git'
            }
        }

        stage("Unit Test"){

            steps{
                sh 'mvn test'
            }
        }

        stage("Integration Test"){
            steps{ sh 'mvn verify -DskipUnitTests'}
        }

        stage("Continous Build"){  
            steps{ sh 'mvn clean install'}
        }

        stage("Static Test Analysis"){  
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'Sonar-Token') {
                       // some block
                       sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }

    }
}
