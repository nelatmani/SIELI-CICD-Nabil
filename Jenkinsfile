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
    }
}
