pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from version control (e.g., Git)
                //git checkout scm
            }
        }
        
        stage('Build') {
            steps {
                // Build the project (e.g., compile code, run tests)
                //sh 'mvn clean install'
            }
        }
        
        stage('Test') {
            steps {
                // Run additional tests if needed
                //sh 'mvn test'
            }
        }
		
		stage('Artifactory') {
            steps {
                // Run the artifactory
         
            }
        }
        
        stage('Deploy to dev') {
            when {
                branch 'dev'
            }
            steps {
                // Deploy to the development environment
                //sh 'kubectl apply -f dev-deployment.yaml'
            }
        }
        
        stage('Deploy to feature1') {
            when {
                branch 'feature1'
            }
            steps {
                // Deploy to the QA environment
                //sh 'kubectl apply -f qa-deployment.yaml'
            }
        }

	stage('Deploy to feature2') {
            when {
                branch 'feature2'
            }
            steps {
                // Deploy to the QA environment
                //sh 'kubectl apply -f qa-deployment.yaml'
            }
        }

        
        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                // Deploy to the production environment
                //sh 'kubectl apply -f prod-deployment.yaml'
            }
        }
    }
    
    post {
        success {
            // Notify on successful build and deployment
            echo 'Build and deployment successful!'
        }
        failure {
            // Notify on build or deployment failure
            echo 'Build or deployment failed. Please check the logs.'
        }
    }
}
