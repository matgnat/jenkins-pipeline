pipeline {
    agent any
    tools {
        maven 'maven_3.8.5'
    }
    parameters {
        string(name: 'ENV', defaultValue: 'nuke-dev', description: 'environment to run test on') 
        choice(name: 'ENV', choices: ['nuke-dev','nuke-demo','br-sit','nuke-pre-prod','azure'])
    }
    environment {
        NEW_VERSION = '1.3.0'
    }
    stages{
        stage('Build'){
            steps{
                echo 'execute stage BUILD'
                echo "building version ${NEW_VERSION}"
            }         
        }
        stage('Test'){
            when {
                expression {
                    env.BRANCH_NAME == 'main' // steps will be executed if expression pass
                }
            }
            steps{
                echo 'execute stage TEST'
                sh "mvn -ENV=${ENV}"
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
