pipeline {
    agent any
    stages{
        stage('Build'){
            steps{
                echo 'execute stage BUILD'
            }         
        }
        stage('Test'){
            when {
                expression {
                    env.BRANCH_NAME = 'master' // steps will be executed if expression pass
                }
            }
            steps{
                 echo 'execute stage TEST'
            }         
        }
        stage('Deliver'){
            steps{
                echo 'execute stage DELIVER'
            }         
        }
    }
  post{
    always{
        echo 'post - always'
      //run as postcondition no matter what job results 
    }
    failure{
        echo 'post - failure'
    }
  }
}
