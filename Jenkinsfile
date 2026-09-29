pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'flutter pub get'
            }
        }

        stage('Test') {
            steps {
                bat 'flutter test'
            }
        }

        stage('Build') {
            steps {
                bat 'flutter build apk --release'
            }
        }

        stage('Archive APK') {
            steps {
                archiveArtifacts artifacts: 'build\\app\\outputs\\flutter-apk\\app-release.apk',
                                 fingerprint: true
            }
        }
    }
}