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
                echo "Building the code using Jenkins..."
                
            }
            post{
                success{
                    echo 'The build was successful!'
                    mail to: 'mebram51@gmail.com', subject: 'Build Successful', body: 'The build was successful!'
                }
                failure{
                    echo 'The build failed!'
                    mail to: 'mebram51@gmail.com', subject: 'Build Failed', body: 'The build failed!'
                }
            }
        }
        stage('Unit and Integration Tests '){
            steps{
                echo "Running unit tests using Jenkins..."
                echo "Running integration tests using Jenkins..."
            }
        }

        stage('Code Analysis '){
            steps{
               echo "Analyzing the code using Jenkins static code analysis tools..."
            }
        }
        stage('Security Scan '){
            steps{
                echo "Performing security scan using Jenkins security scan plugins(e.g., probely plugin)..."
        }
        }
        stage('Deploy to Staging'){
            steps{
                echo "Deploying the application to a staging server (e.g., AWS EC2 instance)..."
            }
            post{
                success{
                    echo 'The deployment to staging was successful!'
                    mail to: 'mebram51@gmail.com',       subject: 'Deployment to Staging Successful', body: 'The deployment to staging was successful!'
                }
                failure{
                    echo 'The deployment to staging failed!'
                    mail to: 'mebram51@gmail.com', subject: 'Deployment to Staging Failed', body: 'The deployment to staging failed!'
            }
        }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo "Running integration tests on the staging environment..."
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploying the application to a production server (e.g., AWS EC2 instance)..."
                }
                post{
                    success{
                        echo 'The deployment to production was successful!'
                        mail to: 'mebram51@gmail.com', subject: 'Deployment to Production Successful', body: 'The deployment to production was successful!'
                       
                    }
                    failure{
                        echo 'The deployment to production failed!'
                        mail to:    'mebram51@gmail.com', subject: 'Deployment to Production Failed', body: 'The deployment to production failed!'
                
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
}
