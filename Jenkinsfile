pipeline {
    agent any

    tools {
        // The name should match the Maven installation configured in your Jenkins
        maven 'maven-in-opt'
    }

    stages {
        stage('Checkout') {
            steps {
                // Replace with your GitHub project URL
                git 'https://github.com/yourname/yourproject.git'
            }
        }

        stage('Build with Maven') {
            steps {
                // Maven build
                sh 'mvn clean install'
            }
        }

        stage('Deploy to Nexus') {
            steps {
                // Push artifacts to Nexus
                // Replace 'your-nexus-repository' with your actual Nexus repository ID
                sh 'mvn deploy -DaltDeploymentRepository=your-nexus-repository::default::http://nexus-url:8081/repository/your-nexus-repository/'
            }
        }
    }
}
