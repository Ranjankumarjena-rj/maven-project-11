pipeline {
    agent { label 'sleve-3-win' }

    tools {
        maven 'M2_HOME'     // Maven name as configured in Jenkins
        jdk 'JAVA_HOME'        // JDK name as configured in Jenkins
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/Ranjankumarjena-rj/maven-project-11.git'
            }
        }

        stage('Maven install') {
            steps {
                bat 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build and install completed successfully'
        }
        failure {
            echo 'Build failed'
        }
    }
}
