pipeline{
    agent any

    stages {

        stage('Flutter Clean'){
            steps{
                sh 'flutter doctor'
            }
        }
        stage('Build Debug Flutter') {
            steps {
                sh 'sudo flutter build apk --debug'
            }
        }
        stage('Build Release FAT Flutter'){
            steps{
                sh 'sudo flutter build apk --release' 
            }
        }

        // stage("Build debug ios Flutter"){
        //     steps{
        //         sh 'flutter build ios --debug'
        //     }
        // }
        
    }

    post{
        always{
            archiveArtifacts artifacts: 'build/app/outputs/apk/**/*.apk', fingerprint: true, onlyIfSuccessful: true, defaultExcludes: true, allowEmptyArchive: true
            archiveArtifacts artifacts: 'build/app/outputs/app/**/*.app', fingerprint: true, onlyIfSuccessful: true, defaultExcludes: true, allowEmptyArchive: true
        }
        
    }
}