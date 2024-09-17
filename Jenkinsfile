pipeline {
    agent any
    stages{
        /*stage('Build docker image'){
            steps{
                script{
                    sh 'docker buildx build --tag ndzenyuy/staticweb:${BUILD_ID} .' 
                }
            }
        }*/

        stage('Build Docker Image'){
            steps {
                script {
                    dockerImage = docker.build( "ndzenyuy/staticwebsite" + ":$BUILD_NUMBER", ".")
                }
            }
        }

        stage('Upload App Image') {
          steps{
            script {
               withDockerRegistry([ credentialsId: "dockerlogin", url: ""]){
                dockerImage.push("$BUILD_NUMBER")
                dockerImage.push('latest')
               }              
              
            }
          }
        } 

        
        
    }
}