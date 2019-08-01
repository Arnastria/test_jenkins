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
                echo 'flutter build apk --debug'
            }
        }
        stage('Build Release FAT Flutter'){
            steps{
                echo 'flutter build apk --release'
            }
        }
    }
}