pipeline {
 
    stages {
        stage("Checkout"){
        }

        stage("Install dependencies"){
            steps{
                script{
                    bat "npm install"
                }
            }
        }

        stage("Start Application and run tests"){
            steps{
                script{
                    bat "start /b npm start"
                }
            }
        }

        stage ("run tests"){
            steps{
                script{
                    bat "start npm test"
                }
            }
        }
    }

    post {
        always{
            echo "CI pipeline complited"
        }
    }
}