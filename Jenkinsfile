pipeline {
    agent any

    environment {
        FIREBASE_TOKEN = credentials('FIREBASE_TOKEN')
    }

    stages {
        stage('Deploy to Testing') {
            steps {
                sh 'firebase deploy --only hosting:testing --token "$FIREBASE_TOKEN"'
            }
        }

        stage('Deploy to Staging') {
            steps {
                sh 'firebase deploy --only hosting:staging --token "$FIREBASE_TOKEN"'
            }
        }

        stage('Deploy to Production') {
            steps {
                sh 'firebase deploy --only hosting:production --token "$FIREBASE_TOKEN"'
            }
        }
    }
}

