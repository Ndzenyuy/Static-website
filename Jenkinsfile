pipeline {
    agent any
    stages{
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker buildx build --tag ndzenyuy/staticweb:${BUILD_ID} .' 
                }
            }
        }

        /*stage('Stop any running containers'){
            steps{
                script{
                    sh 'docker stop $(docker ps -q)'
                }
            }
        }*/

        stage('Run docker Container'){
            steps{
                script{
                    sh 'docker run -d -p 80:80 ndzenyuy/staticweb:${BUILD_ID}'
                }
            }
        }
        
    }
}
