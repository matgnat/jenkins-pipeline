pipeline {
    agent any
    stages{
        stage('Build'){
            steps{

            }         
        }
        stage('Test'){
            when {
                expression {
                    env.BRANCH_NAME = 'master' // steps will be executed if expression pass
                }
            }
            steps{

            }         
        }
        stage('Deliver'){
            steps{

            }         
        }
    }
  post{
    always{
      //run as postcondition no matter what job results 
    }
    failure{
    }
  }
}
