pipeline {
    agent any

    tools {
	nodejs 'NodeJS4.8.6'
    } 
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') { 
            steps {
                sh 'npm install'
		sh 'npm test'
            }
        }
        stage('Deploy') { 
            steps {
                sh 'npm install'
		sh 'npm run package'
		archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
            }
        }
    }
}
