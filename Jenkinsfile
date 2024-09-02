pipeline {
    agent any
    stages{
        stage('Deploy to server'){
            steps{
                script{
                    sh 'sudo rm -rf /var/www/html/*'
                    sh 'sudo cp -r Static-website/ /var/www/html/'
                    sh 'sudo systemctl restart apache2'
                }
            }
        }
    }
}