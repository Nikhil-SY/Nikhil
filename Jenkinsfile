pipeline{
    agent any
    stages{
        stage('Stage 1'){
            steps{
                sh 'pwd'
            }
        }
        stage('Stage 2'){
            steps{
                sh '''
                whoami
                date
                ls
                '''
            }
        }
    }
}