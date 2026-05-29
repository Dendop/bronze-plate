pipeline{
    agent any

    // environment{

    // }
    // parameters{

    // }
    options{
        timestamps()
        timeout(time: 5, unit: 'MINUTES')
    }
    stages{
        stage('make directory'){
            options{
                retry(2)
            }
            steps{
                sh "mkdir  ~/jenkins-pipeline-example || true"
                sh "cd jenkins-pipeline-example"
                sh "echo 'Hello World' > exampleFile.txt || true"
            }
        },
        stage('adding a new file'){
            steps{
                sh "touch ~/jenkins-pipeline-example/newFile.txt || true"
            }
        }
    }
    post{
        always{
            archiveArtifacts artifacts: 'jenkins-pipeline-example/*', allowEmptyArchive: true
        }
    }
}