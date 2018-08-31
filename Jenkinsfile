pipeline {
   
    agent { label 'salam' }

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
       
       stage('Scanning'){
            steps{
                parallel(
                    'PMD': {
                        echo "PMD Scanning"
                    },
                    'Checkmarx': {
                        echo "Security Testing"
                    } 
                )
            }
        }

       stage('Unit Testing'){
            steps{
                echo "Start JUnit"
            }
        }
       stage('Deploy'){
            steps{
                echo "Start Deployment"
             }
        }
      stage('Sanity'){
            steps{
                parallel(
                    'Login': {
                        echo "Login"
                    },
                    'Home': {
                        echo "Home"
                    }
                   'Review': {
                        echo "Home"
                    } 
                )
            }
        }
    }
}
