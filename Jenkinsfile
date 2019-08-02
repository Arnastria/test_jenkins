pipeline{
    agent any

    stages {

        stage('Flutter Clean'){
            steps{
                sh 'source ~/.bashrc'
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

        stage("Build debug ios Flutter"){
            steps{
                sh 'flutter build ios --debug'
            }
        }
        
    }

    post{
        always{
            archiveArtifacts artifacts: 'build/app/outputs/apk/**/*.apk', fingerprint: true, onlyIfSuccessful: true, defaultExcludes: true, allowEmptyArchive: true
            archiveArtifacts artifacts: 'build/app/outputs/app/**/*.app', fingerprint: true, onlyIfSuccessful: true, defaultExcludes: true, allowEmptyArchive: true
        }
        
    }
}