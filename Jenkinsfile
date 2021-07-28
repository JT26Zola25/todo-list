pipeline {
    agent any
    enviroment {
        DATABASE_URI = credentials("DATABASE_URI")
        SECRET_KEY = credentials("SECRET_KEY")
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh "bash jenkins/install.sh"
        }
    }
        stage('Testing') {
            steps {
                "bash jenkins/test.sh"
        }
    } 
        stage('Deploy') {   
            steps {  
                sh 'python3 create.py'
                sh 'bash jenkins/deploy.sh'
            }
        }
    }    
    // post {
    //     always {
    //     }
    // }
}