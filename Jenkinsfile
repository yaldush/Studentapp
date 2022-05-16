pipeline {
    agent any
    stages {
        stage('github-clone') {
            steps {
                git changelog: false, credentialsId: 'github', poll: false, url: 'https://github.com/yaldush/Studentapp.git'
            }
		}
        stage('maven-clean') {
            steps {
                sh 'mvn clean'
            }
		}
        stage('maven-build') {
            steps {
                sh 'mvn package'
            }
		}
      /*  stage('maven-sonarqube') {
            steps {
                
            }
		} */
        stage('mvn-nexus-backup') {
            steps {
                sh 'mvn deploy'    
            }
		}

    }
}
