pipeline{
    agent any
    parameters{
        booleanParam(name:"Devops", description:"Check if you are from devops team")
    }
    environment{
        Team="DevOps"
    }
    stages{
        stage('Pre-stage'){
            steps{
                sh 'exit 1'
                }
        }
        stage('Parallel Job'){
            steps{
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
                        echo "Team: ${Team}"
                        '''
                        }
                }
            }
    }
         stage('Stage 3'){
                steps{
                    sh 'exit 1'
                    }
}
}
}
