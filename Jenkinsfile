pipeline {
    agent any
    
    stages {
        stage('Clone Code') {
            steps {
                script {
                    echo "Cloning code from branch: ${env.BRANCH_NAME}"
                    // For public repo - code is already cloned by Jenkins
                    echo "Repository cloned successfully!"
                }
            }
        }
        
        stage('Hello World') {
            steps {
                script {
                    echo "Hello World from branch: ${env.BRANCH_NAME}"
                    echo "Build number: ${env.BUILD_NUMBER}"
                    echo "Job name: ${env.JOB_NAME}"
                }
            }
        }
        
        stage('Branch-Specific Tasks') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'master') {
                        echo "Running production tasks..."
                    } else if (env.BRANCH_NAME == 'develop') {
                        echo "Running development tasks..."
                    } else {
                        echo "Running feature branch tasks..."
                    }
                }
            }
        }
    }
    
    post {
        success {
            echo "Pipeline completed successfully! ✓"
        }
        failure {
            echo "Pipeline failed! ✗"
        }
    }
}
