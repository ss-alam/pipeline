pipeline {
   
    agent { label 'master' }

    stages {
        stage('Clone'){
            steps{
                echo "Start Cloning by getting code from GIT"
            }
        }
       
        stage('Build'){
            steps{
                echo "Start Build"
            }
        }
       
       stage('Scan'){
            steps{
                parallel(
                    'PMD': {
                        echo "PMD"
                    },
                    'Checkmarx': {
                        echo "Security"
                    } 
                )
            }
        }

       stage('Unit Test'){
            steps{
                echo "Start JUnit"
            }
        }
       stage('Deploy'){
            steps{
                echo "Start Deployment"
             }
        }
      stage('UI Test'){
            steps{
                parallel(
                    'Login': {
                        echo "Login"
                    },
                    'Home': {
                        echo "Home"
                    },
                   'Review': {
                        echo "Review"
                    } 
                )
            }
        }
    }
}
