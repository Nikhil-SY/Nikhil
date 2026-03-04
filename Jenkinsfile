pipeline{
    agent any
    parameters{
        booleanParam(name:"Devops", description:"Check if you are from devops team")
        choice(name:"Environment",choices:["Dev","QA","Prod"], description:"Select the environment")
    }
    environment{
        Team = "DevOps"
    }
    stages{
        stage('Pre-stage'){
            steps{
                catchError(buildResult: "SUCCESS", stageResult: "FAILURE"){
                sh 'exit 1'
                }
            
        }
        }
        stage('Parallel Job'){
            parallel{
                stage('Stage 1'){
                    when{
                    expression { params.Environment == "Prod" }
                }
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
                catchError(buildResult: "SUCCESS", stageResult: "FAILURE"){
                sh 'exit 1'
                }
}
}
}
}
