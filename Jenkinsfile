pipeline{
    agent any

    stages {

        stage('Flutter Clean'){
            steps{
                sh 'flutter clean'
            }
        }
        stage('Build Debug Flutter') {
            steps {
                sh 'flutter build apk --debug'
            }
        }
        stage('Build Release FAT Flutter'){
            steps{
                sh 'flutter build apk --release'
            }
        }
        
    }

    post{
        always{
            archiveArtifacts artifacts: 'build/app/outputs/apk/**/*.apk', fingerprint: true, onlyIfSuccessful: true, defaultExcludes: true, allowEmptyArchive: true
        }
        
    }
}