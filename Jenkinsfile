pipeline {
    agent any 
    stages {
        stage('checkout') { 
            steps {
                 git credentialsId: '1b7f4df4-7ff7-4f82-9778-34c154fcde05', url: 'https://github.com/chinnari321/pipelin.git'

            }
        }
        stage('Build') { 
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') { 
            steps {
                s3Upload consoleLogLevel: 'INFO', dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'bucket12456', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-east-1', showDirectlyInBrowser: false, sourceFile: '**/*.war', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'SUCCESS', profileName: 'bucket', userMetadata: []
            }
        }
    }
}
