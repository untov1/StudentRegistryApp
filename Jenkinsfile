pipeline {
    agent eny

    environment {
        NODE_VERSION = "20.x"
    }

    tools {
        nodejs "${NODE_VERSION}"
    }

    stages {
        stage("Checkout"){
            steps{
                checkout scm
            }
        }

        stage("Install dependencies"){
            steps{
                script{
                    if(isUnix()){
                        sh "npm install"
                    }
                    else {
                        sh "npm install"
                    }
                }
            }
        }

        stage("Start Application and run tests"){
            steps{
                script{
                    sh "npm start &"
                    sh "wait-on http://localhost:8090"
                    sh "npm test"
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