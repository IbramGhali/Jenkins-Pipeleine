pipeline{
    agent any
     environment {
        DIRECTORY_PATH = 'C:\\Users\\ebram\\OneDrive - Deakin University\\1.Study Material\\2024\\Trimester 1\\SIT753 - PROFESSIONAL PRACTICE IN INFO TECH\\Week 6\\3.tasks\\SIT223_SIT753-6.1C'
        TESTING_ENVIRONMENT = 'QA'
        PRODUCTION_ENVIRONMENT = 'Ibram_Ghali'
    }
    stages{
        stage('Build'){
            steps{
               echo 'fetch the source code from the directory path specified by the environment variable'
                echo 'compile the code and generate any necessary artifacts'
            }
        }
        stage('Unit and Integration Tests '){
            steps{
                echo 'unit tests...'
                echo 'integration tests....'
            }
        }

        stage('Code Analysis '){
            steps{
               echo 'check the quality of the code.....'
            }
        }
        stage('Security Scan '){
            steps{
                echo 'Testing the project'
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo 'Deploying the project'
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo 'Deploying the project'
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploying the code to the production environment (${env.PRODUCTION_ENVIRONMENT})..."
                }
        }
    }
    post{
        always{
            echo 'This will always run'
        }
        success{
            echo 'This will run only if the build is successful'
            mail to: 'mebram51@gmail.com', subject: '${env.JOB_NAME} - Build # ${env.BUILD_NUMBER} - Successful', body: 'Congratulations! Your build was successful.'
        }
        failure{
            echo 'This will run only if the build fails'
            mail to: 'mebram51@gmail.com', subject: '${env.JOB_NAME} - Build # ${env.BUILD_NUMBER} - Failed', body: 'We are sorry, your build has failed.'
        }
        
        unstable{
            echo 'This will run only if the build is unstable'
            mail to: 'mebram51@gmail.com', subject: '$JOB_NAME - Build # $BUILD_NUMBER - Unstable', body: 'Your build is unstable.'
        }
        changed{
            echo 'This will run only if the build status changes'
            mail to: 'mebram51@gmail.com', subject: '$JOB_NAME - Build # $BUILD_NUMBER - Status Changed', body: 'The build status has changed.'
        }
    }
}