pipeline {
    agent any
    stages{
        stage('Deploy to server'){
            steps{
                script{
                    sh 'sudo rm -rf /var/www/html/*'
                    sh 'ls'
                    sh 'sudo cp -r . /var/www/html/'
                    sh 'sudo systemctl restart apache2'
                }
            }
        }
    }
}