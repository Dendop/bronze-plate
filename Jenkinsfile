pipeline {
    agent any

    options {
        timestamps()
        timeout(time: 5, unit: 'MINUTES')
    }

    stages {

        stage('Prepare folder') {
            steps {
                sh 'mkdir -p jenkins-pipeline-example'
                sh 'echo "Hello World" > jenkins-pipeline-example/exampleFile.txt'
            }
        }

        stage('Add file') {
            steps {
                sh 'touch jenkins-pipeline-example/newFile.txt'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'jenkins-pipeline-example/*', allowEmptyArchive: true
        }
    }
}