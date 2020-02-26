/* import shared library */
@Library('Jenkins-Shared-Library')_
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
post {
        always {
	    /* Use slackNotifier.groovy from shared library and provide current build result as parameter */   
            slackNotifier(currentBuild.currentResult)
            cleanWs()
        }
    }
}
