pipeline {
    agent any
    stages{
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker buildx build --tag ndzenyuy/staticWeb:${BUILD_ID} .'
                }
            }
        }

        stage('Run docker Container'){
            steps{
                script{
                    sh 'docker run -d -p 80:80 staticWeb:${BUILD_ID}'
                }
            }
        }
        
    }
}